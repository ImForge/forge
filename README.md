# Forge — Knowledge doesn't graduate.

Forge is the permanent project-sharing and knowledge-preservation platform for ITM University Raipur. Every project submitted outlives its creator's time here — available for every future student to discover, study, and build upon.

---

## What it does

- **Archive projects** — Students submit their work permanently. Solo or team, with documentation, GitHub links, live demos, and faculty guide attribution.
- **Build-on system** — Projects can be linked to previous student work, creating a visible knowledge lineage tree across batches and years.
- **Teams** — Create or join teams, invite members, share resources (GitHub, Figma, Drive), submit collaborative projects.
- **Assignments** — Upload and share academic resources publicly or keep them private.
- **Admin panel** — Approve/reject submissions, manage tags, manage users.

---
check it out https://itmshowcase.vercel.app/
Testing Email- testing@gmail.com
Password- 12345
## Tech Stack

| Layer | Tech |
|---|---|
| Framework | Next.js 15.3.2 (App Router, TypeScript, Turbopack) |
| Database | Supabase (PostgreSQL + RLS) |
| Auth | Supabase Auth (OTP email flow) |
| Storage | Supabase Storage |
| Styling | Tailwind CSS v4 + inline CSS variables |
| Fonts | Cormorant Garamond + DM Sans (next/font) |
| Deployment | Vercel (live) |

---

---

## Key Design Decisions

**No thumbnails** — project cards use deterministic cinematic gradients based on the project title. Keeps the aesthetic consistent and avoids broken image links.

**Server + Client split** — pages that only display data are Server Components (faster, SEO friendly). Pages with filters, forms, or interactivity are Client Components. Event handlers are never passed across the boundary.

**`proxy.ts` not `middleware.ts`** — Next.js 15 naming convention for the middleware file.

**Supabase FK hints** — all joins use explicit FK hints (e.g. `profiles!projects_submitted_by_fkey`) to avoid ambiguous relationship errors.

**Programs and semesters** — BCA has 6 semesters, B.Tech has 8. The semester dropdown updates based on the selected program. Stored in `profiles.program` and `projects.program`.

---

## Deployment

Deployed on Vercel. After pushing to GitHub, Vercel auto-deploys on every push to `main`.

Environment variables must be set in Vercel → Project Settings → Environment Variables.

After deployment, update Supabase → Authentication → URL Configuration with your Vercel URL.

---


> *"Every project submitted is a letter to the next generation."*
