# AI CTO | Project History Architecture & Component Specification

## Data Model (Supabase Integration Ready)
```json
{
  "id": "uuid",
  "user_id": "uuid",
  "title": "string",
  "prompt": "string",
  "response": "string",
  "timestamp": "iso_timestamp",
  "type": "PRD | UI_UX | BACKEND | PLAN | CODE",
  "metadata": {
    "tokens": "number",
    "model": "string",
    "confidence": "number"
  }
}
```

## History Component Specifications
- **Sidebar Drawer:** Persistent on desktop, collapsible slide-over for mobile.
- **Search Engine:** Client-side fuzzy search for title and prompt content.
- **State Management:**
    - `loading`: Shimmer skeleton loader for list items.
    - `empty`: "Blank Slate" illustration with "Start Generating" CTA.
    - `active`: Highlighted state for the currently viewed generation.
- **Persistence Hooks:**
    - `saveGeneration()`: Function stub to POST to `/api/history`.
    - `fetchHistory()`: Function stub to GET from `/api/history`.
    - `deleteGeneration()`: Function stub for DELETE requests.

## Visual Tokens (Obsidian Nexus)
- **Background:** `bg-[rgba(20,20,20,0.7)] backdrop-blur-2xl`
- **Border:** `border-white/5`
- **Accent:** `text-primary (purple-400)` with `shadow-[0_0_15px_rgba(168,85,247,0.4)]`
- **Typography:** Inter (Sans), JetBrains Mono (Code/Timestamps)
