# AI CTO | Supabase Integration & Database Schema

## Database Collections (Supabase Tables)

### `users`
- `id`: uuid (primary key)
- `email`: string
- `created_at`: timestamp
- `subscription_tier`: enum (FREE, PRO, TEAM)

### `projects`
- `id`: uuid (primary key)
- `user_id`: uuid (foreign key -> users.id)
- `title`: string
- `created_at`: timestamp
- `updated_at`: timestamp
- `status`: string (ACTIVE, ARCHIVED)

### `generations`
- `id`: uuid (primary key)
- `project_id`: uuid (foreign key -> projects.id)
- `type`: enum (PRD, UI_UX, BACKEND, PLAN, CODE)
- `prompt`: text
- `response`: text
- `metadata`: jsonb (tokens, model, confidence)
- `created_at`: timestamp

### `autosaves`
- `project_id`: uuid (primary key, foreign key -> projects.id)
- `content_snapshot`: jsonb
- `updated_at`: timestamp

### `usage_logs`
- `id`: uuid (primary key)
- `user_id`: uuid (foreign key -> users.id)
- `action`: string
- `tokens_used`: number
- `timestamp`: timestamp

## Service Layer (Lib/supabase.js)

```javascript
// Placeholder for Supabase Client Initialization
// import { createClient } from '@supabase/supabase-js'
// const supabase = createClient(URL, KEY)

export const db = {
  // Projects
  async fetchProjects(userId) {
    const { data, error } = await supabase
      .from('projects')
      .select('*, generations(*)')
      .eq('user_id', userId)
      .order('updated_at', { ascending: false });
    return { data, error };
  },

  // Generations
  async saveGeneration(projectId, generationData) {
    const { data, error } = await supabase
      .from('generations')
      .insert([{ project_id: projectId, ...generationData }]);
    
    // Update project timestamp
    await supabase.from('projects').update({ updated_at: new Date() }).eq('id', projectId);
    
    return { data, error };
  },

  // Real-time Sync
  subscribeToProject(projectId, callback) {
    return supabase
      .channel(`project:${projectId}`)
      .on('postgres_changes', { event: '*', filter: `project_id=eq.${projectId}` }, callback)
      .subscribe();
  }
};
```