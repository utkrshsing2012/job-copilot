# job-copilot

Next.js 16 (App Router) + React 19 + Tailwind 4 + shadcn/ui. Backend: Supabase (auth + db), Stripe (payments), Vercel AI SDK with @ai-sdk/anthropic. Uses pnpm. Early scaffold: app/page.tsx is still the default page.

## Commands
```
pnpm install
pnpm dev        # http://localhost:3000
pnpm lint
pnpm build      # run before claiming a change works
```

## Layout
- app/           routes, layout.tsx, globals.css
- components/ui  shadcn components (generate with `pnpm dlx shadcn add <name>`, do not hand-write)
- lib/utils.ts   cn() helper

## Rules
- Env vars go in .env.local (gitignored). Supabase/Stripe/Anthropic keys never in code.
- Server-only secrets must stay in server components, route handlers, or server actions. Never prefix them NEXT_PUBLIC_.
- Use the Anthropic model id claude-sonnet-5-5 by default unless told otherwise.
- Keep components small; prefer server components unless interactivity is needed.
