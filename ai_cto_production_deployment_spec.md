# AI CTO | Production Deployment & Vercel Configuration

## Environment Variables (.env.production)
The following variables must be configured in the Vercel dashboard:

```env
# Supabase Configuration
NEXT_PUBLIC_SUPABASE_URL=https://gisikbdmqzlqbconkqod.supabase.co
NEXT_PUBLIC_SUPABASE_ANON_KEY=sb_publishable_P1EvsTFoF1dfVlCHmAULHw_bQG4MYmH

# Backend API Configuration
NEXT_PUBLIC_BACKEND_API_URL=https://node-core--khan18aees.replit.app

# Analytics & Monitoring
NEXT_PUBLIC_ANALYTICS_ID=cto_prod_nexus_v4
```

## Vercel Configuration (vercel.json)
```json
{
  "version": 2,
  "framework": "nextjs",
  "regions": ["sfo1"],
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "X-Content-Type-Options", "value": "nosniff" },
        { "key": "X-Frame-Options", "value": "DENY" },
        { "key": "X-XSS-Protection", "value": "1; mode=block" }
      ]
    }
  ],
  "redirects": [
    { "source": "/login", "destination": "/", "permanent": false }
  ]
}
```

## Production Routing & Middleware
1. **Auth Guard:** All routes under `/workspace/*` and `/dashboard/*` are protected by Supabase Auth middleware.
2. **Fallback Logic:** Unauthenticated requests to protected routes are redirected to `{{DATA:SCREEN:SCREEN_27}}`.
3. **Success Redirect:** Successful OAuth handshakes redirect to `{{DATA:SCREEN:SCREEN_51}}`.

## Reliability Layers
- **Error Boundaries:** Custom Obsidian Nexus themed error screens for 404 and 500 errors.
- **Loading Fallbacks:** Shimmer skeletons integrated into all data-fetching components (Projects, Analytics, History).
- **Backend Health Check:** Automated handshake with the Node.js API before initiating generations.