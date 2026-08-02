# Secrets & API keys (safe pattern)

## Never do this
- Do **not** paste API keys into chat or commit them to GitHub
- Do **not** put secret keys in `NEXT_PUBLIC_*` (browser-visible)

## Do this
1. Open **Xroga → Integrations**
2. Paste your key (OpenAI, Stripe, Supabase, custom…) → **Save**
3. Keys are stored **AES-256-GCM encrypted** in your account
4. When you deploy with **Vercel connected**, Xroga upserts them as project env vars
5. In code, read `process.env.OPENAI_API_KEY` (server/API routes only)

## Free client-safe APIs (optional demos)
Some public APIs work in the browser without secrets (e.g. demo image APIs). Prefer server routes for anything paid or private.

### No keys saved yet
Add one under Integrations before shipping paid AI/features.
