# AI CTO | Environment Configuration (.env.local)

## Supabase Integration
```env
NEXT_PUBLIC_SUPABASE_URL=https://YOUR-PROJECT.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=YOUR_PUBLISHABLE_KEY
```

## Usage Instructions
These environment variables are required for initializing the Supabase client in `lib/supabase.js`.
- **URL:** The unique API endpoint for your Supabase project.
- **Anon Key:** The publishable key used for client-side authentication and Row Level Security (RLS).