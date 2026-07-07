# agentlab — architecture ground truth

Updated by dev sessions whenever a change alters the design. Empty (below the constraints) means greenfield.

## Platform constraints (do not violate)
- Hosting: Cloudflare Pages, STATIC files only. No server/backend/database/paid services/accounts. All logic runs client-side in the browser. Never fetch() a backend — it 404s.
- Multiplayer: WebRTC peer-to-peer (free), one authoritative host. Never a server; never turn-based for a real-time game.
- No build step: inline single-file HTML or CDN imports (esm.sh/unpkg); no `npm install` at runtime. Keep index.html at the project ROOT (flat) — a nested client/+server/ layout once shipped a 404.
- Assets: Canvas/CSS/SVG/emoji + Web Audio; player-supplied images live in assets/. Persistence via localStorage. Assume mobile/touch.

## Current design
- `index.html` (project root): single self-contained static page. Displays "agent loop lives"
  as a hello-world / deploy-pipeline smoke test. All styling inline, zero external requests.
  This is the current entry point and the template to follow for the flat single-file layout.
