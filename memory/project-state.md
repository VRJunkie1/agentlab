# agentlab — current state

Goals, open threads, recent decisions. Refreshed at the end of each dev session.

## Goals
- Prove the end-to-end pipeline works (plan → build → deploy to Cloudflare Pages) before
  investing in bigger builds. A hello-world page is the smallest thing that validates it.

## Recent decisions
- 2026-07-07: Shipped `index.html` at the project ROOT — a self-contained "agent loop lives"
  hello-world page. Flat layout deliberately (nested layouts have 404'd before). All CSS
  inline, no external fetches, no libraries. Dark background + monospace + a pulsing green
  status dot so it reads as intentional, not broken. Mobile-safe: viewport meta with
  viewport-fit=cover, 100dvh height, fluid clamp() type.

## Open threads
- Deploy: confirm the live Cloudflare Pages URL renders the page. This is the real point of
  the exercise — it de-risks every future build. (Deploy is done outside this coding session.)
- `assets/attached_0.png` (low-poly burger renders) is in the repo but unused — appears to be
  reference art for a future build, not for this page.
