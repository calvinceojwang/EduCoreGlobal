# EduCore Training Hub

React + Vite frontend with Supabase-backed authentication, dashboards, and training workflows.

## Authentication

- Supabase email/password sign-in only
- Internal redirects only:
  - `/dashboard` for standard users
  - `/admin-dashboard` for admin users
- Custom forgot/reset password flow using `/forgot-password` and `/reset-password`
- Minimum password length enforced on frontend and backend: 6 characters

## Local Development

```bash
npm install
npm run dev
```

## Environment Variables

Create `.env` and provide:

- `VITE_SUPABASE_URL`
- `VITE_SUPABASE_PUBLISHABLE_KEY`

For API route deployments, also configure:

- `SUPABASE_URL` (or `VITE_SUPABASE_URL`)
- `SUPABASE_PUBLISHABLE_KEY` (or `VITE_SUPABASE_PUBLISHABLE_KEY`)

