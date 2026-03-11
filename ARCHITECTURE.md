# Architecture Conventions

## Layering

- `src/ui`
- UI-level exports and composition helpers used by pages/components.
- Contains no Supabase or backend access code.

- `src/pages` and `src/components`
- Presentation and feature orchestration only.
- Calls service functions for backend/database operations.

- `src/services`
- Application service layer for auth, edge functions, and data queries/mutations.
- This is the only layer (besides `src/integrations`) allowed to use Supabase client APIs directly.

- `src/domain`
- Shared domain types and interfaces.
- No framework or backend client imports.

- `src/data`
- Static/local datasets for UI rendering.
- No backend client imports.

## Current Rule

- Do not call `supabase.from(...)`, `supabase.rpc(...)`, or `supabase.functions.invoke(...)` from `src/pages`, `src/components`, or `src/hooks`.
- Route such operations through `src/services/*`.
