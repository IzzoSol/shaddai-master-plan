# SHADDAI — MASTER PLAN FOR OPUS 5.5
**Prepared by QUILL (Writing & Communication) · SHADDAI Council**
**Date:** 2026-11-03 (current session)
**Purpose:** Single source of truth. Everything that is done, everything that is not, how it works, and the exact build order for the Opus 5.5 pass. Supersedes scattered notes. Read this first; then read `shaddai-consultancy/docs/MASTER-PLAN.md` and `shaddai-consultancy/docs/final/FLYWHEEL.md` for the ground-truth economy.

---

## 0. TL;DR (five sentences)

1. SHADDAI is a 3-layer world — a Dashboard command deck, a 2D pixel city, and a 3D realm (Pro-only) — unified by one identity and one Sparks ledger.
2. The money loop is live: money in → Sparks ($1 fixed) → agent work or world purchases → owner earnings → platform cut → funds the world/arcade/creative layer.
3. The 7 council agents (SHADDAI, ZEROX, ORACLE, NEXUS, TURTLE, QUILL, PIKADON) are wired as brains; the consultancy backend is the real engine (x402, PayBox, AURA brain, media engine, MCP, Telegram).
4. The ASIMOV token (paired with NVDAx / NVIDIA stock token) carries a 3% buy/sell tax and "NVIDIA rewards" — this can fund an in-game rewards center that pays out Sparks or Shaddai coin.
5. NFTs: pages exist, badge system plans NFT credentials, but no live NFT economics yet — needs a spec before building.

---

## 1. WHAT IS ACTUALLY DONE (status matrix)

Sources: `SHADDAI-MASTER/FEATURES_BUILT.md`, `FEATURES_COMPLETE.md`, `SHADDAI_v57.77_STATUS.md`, `shaddai-consultancy/docs/STATUS.md`, `shaddai-consultancy/docs/MASTER-TASKBOARD.md`, `shaddai-consultancy/docs/MASTER-PLAN.md` §15 status log, `THURSDAY-HANDOFF.md`.

### 1.1 Core product (Dashboard layer)
- ✅ 7 agents defined with roles, colors, skills (SHADDAI, ZEROX, ORACLE, NEXUS, TURTLE, QUILL, PIKADON)
- ✅ AURA brain on the request path (boxes + search, ingest/search MCP tools)
- ✅ Agent engine live (`agent-engine.js`: runAgentLoop, routeTask, AGENTS, TOOLS)
- ✅ Tool registry + PolicyEngine (tier gating: wallet_transfer, dex_signal denied for free; stripe_charge requires approval)
- ✅ WorkflowEngine (multi-step, approval gates, retries)
- ✅ JobEngine (create, bid, select winner, rate limits, escrow hold/release)
- ✅ PaymentEngine (80/20 split, escrow, settlePayment)
- ✅ Telemetry + audit log (immutable 1000-entry history)
- ✅ Tier system: Free (1k tokens/day, no wallet), Pro ($49/mo, 10k tokens, wallet), Team ($199/mo, unlimited, shared workspace)
- ✅ ORACLE metering (Redis + PostgreSQL, daily reset UTC, soft warnings at 80% for Pro/Team)
- ✅ Auth: JWT signup/login/verify (stub integration pending real Firebase)
- ✅ Stripe checkout + webhook (signature verification, escrow release on confirm)
- ✅ x402 micropayments mounted (ledger + escrow + security)
- ✅ PayBox (non-custodial agent wallet via MoonPay Open Wallet Standard) — guard currently disabled/wrong shape, needs rebuild against real MCP tools
- ✅ Bazaar resale marketplace skeleton (list/buy/purchase routes; dashboard tile exists)
- ✅ Sparks ledger (Stripe→Sparks, work-sessions, reward-engine, games-routes)
- ✅ x402 → Sparks bridge
- ✅ AURA boxed knowledge (ingest/search/boxes MCP tools, Telegram /learn /boxes /ask, PIKADON SSRF guard, metered ingest with 402 paid rail)
- ✅ Media engine (vendored cobalt, rebranded, /api/media fetch+dl, PIKADON guardrails, MCP tools, /media.html capture UI)
- ✅ Combined capture rail (/api/capture: scrape/media/clip, MCP tool, 3-tab UI)
- ✅ Telegram bot (chat, aura learn/boxes, ask with grounded snippets)
- ✅ Dashboard tiles: agent card, home/plot status, training queue, race/arena invites, SPARKS balance, hiring offers, perch/courier jobs
- ✅ 5 themes (Default, Cyber, Ember, Black, Soft) with instant switch
- ✅ Notifications (in-app toast, email via EmailJS, webhook)
- ✅ Analytics dashboard (KPIs, charts, agent performance table)
- ✅ Agent marketplace profiles (search, filter, calendar, booking)
- ✅ Job templates (Build API, Write Content, Design UI, Security Audit, Data Analysis)
- ✅ Dispute resolution (file, evidence, mediation, timeline, refund)
- ✅ Auto-bidding engine (70% bid rate, 30s loop, toggle)
- ✅ Trade signals autopilot (token watchlist, filters, auto-post Telegram/Discord)
- ✅ Twitter thread generator, web research engine, blog post gen
- ✅ Agent broadcast panel (all 7 simultaneously)
- ✅ Keyboard shortcuts (Ctrl+D dock, Ctrl+N post job, Ctrl+B broadcast, Ctrl+T signals)

### 1.2 2D pixel world layer
- ✅ 2D world with regions: city, meadow/farm, beach, forest, desert, suburb, volcano, darkforest (+ arctic, void 3D-only)
- ✅ 2.5D feel: sun/moon + day/night tint, animated water ripples + foam, character shadows, night lamps, birds, vignette, FX chips
- ✅ Fishing minigame (cast 3-12s → STRIKE → SPACE in 1.6s window; Void-Pearl 1-in-100)
- ✅ Arcade building in 2D city + games as venues with Sparks entry fees
- ✅ Arcade score bridge (games postMessage {shdGame, shdScore, shdWin}; parent pays once per paid entry, iframe+origin checked, per-game caps)
- ✅ Agentic NPC dialogs (E on an agent = letterboxed dialog; agent picks quest vs persona + needs + state; trust tiers scale pay)
- ✅ 2D exteriors (per-region facades, venue signs, dusk-to-night windows, door spill, half-res emissive light layer with depth occlusion)
- ✅ Arcade building + offline skate + $0 compression (skate 105→7MB, council heads 53→15MB)
- ✅ One Sparks ledger 2D↔3D (shaddai.sparks + shd_sparks mirror; unified, old key folded in)
- ✅ Tactics v1 (3D Colosseum: CT/AGI turns, stats, BFS move, bot opponents, pot payouts, win-scaling tiers)
- ✅ 3D five-laws #4 swim (surface float) + #5 vessel seating
- ✅ Hoverboard + tricks + Sparks (ollie/flip/360/big-air, HUD, localStorage)
- ✅ Rideable boats, hero switch (H key), roads (light-trail plaza→all realms+colosseum)
- ✅ Walk-in Colosseum foundation (mecha-arena on plateau, E opens spectate/tourney modal, sparks pools ledger)
- ✅ Garage foundation (B at plaza beacon, hovercar 500⚡ + board/car tier upgrades)
- ✅ Game asset pipeline (one-shot generation gates: spec → concept check → canary → ship)

### 1.3 3D world layer (Pro-only)
- ✅ 3D world host (SHADDAI-WORLD-3D.html) with biome centers, sacred geometry [0,0] hexagon
- ✅ 47 GLBs shipped (buildings, mounts, vehicles, props, heroes ×4 + clips)
- ✅ Fal-asset characters in fal-assets (forge roster: engineer, explorer, mage, scout, warrior, gabi)
- ✅ 7 council agents with 24-bone skeletons (idle/run/walk clips only; no combat/dodge/hit/sit/mount clips yet)
- ✅ Static batcher (-15% draw calls), self-hosted three.js + Draco, modulepreload hints
- ✅ Perf: ~2,190 calls / 4.9M tris aerial; ~4,000-6,000 calls street level on LOW
- ✅ Touch action buttons (jump, interact, attack, kick, flip, run, ride, map, view, passive, tray)
- ✅ Collision data (canon-colliders-v4.json: 6189 boxes, no deep overlaps)
- ✅ Home themes per realm (5 kits, enterable, furnished; interiors v3 recipes)
- ✅ World districts (Campus/Commons/Plots/Race) + named streets
- ✅ Realm hazards (castle gas, pit lava, arctic, volcano) + passive/fight mode + Void forced fight
- ✅ Taming + crafting rules; Castle Siege Day rules (dormant until 50 players)
- ✅ Food/drink buffs; footprints (snow/sand); textured grass clumps
- ✅ Fishing rules (realm fish, tension fight); loading slideshow + intro motion + 7 agent slides
- ✅ Phone controls: touch action buttons + existing stick/look

### 1.4 Economy & money
- ✅ Sparks fixed at 1 Spark = $1 USD (never floats)
- ✅ Stripe → Sparks live
- ✅ x402 micropayments mounted
- ✅ Paybox (agent wallet) — routes exist, guard disabled/wrong shape
- ✅ Bazaar resale skeleton
- ✅ Round-up concept (belongs on Stripe rail)
- ✅ Sparks sources/sinks defined (DOC_SPARKS.md): closed-loop, one-way, no cash-out API may ever be added
- ✅ Subscriptions: Free / Pro $30/mo (Pro Signals, ZEROX sentiment, RAG brain) / Max TBD
- ✅ Founders programme described (3 tiers of 100) but numbers blank — needs owner decision
- ✅ Fee-pool concept (plots pay from collected fees, never promised rate) — compliance line drawn
- ✅ NFT surfaces: pages exist (nft-collection.html, collectibles-nft.html); economics do not
- ✅ Badge system: 5 tiers (Prospect→Grandmaster), Quill-rewritten curriculum (12/52 lessons), badge minting via MCP smart contract

### 1.5 Security
- ✅ PIKADON middleware live (caps, allowlist concepts)
- ✅ Auth guard (softAuth, REQUIRE_AUTH)
- ✅ Sparks shared-balance bug FIXED (economy-identity.js strict precedence; 12/12 tests)
- ✅ PIKADON SSRF guard (https-only, private IP blocked, path blocking, per-box chunk cap)
- ✅ Media engine PIKADON guardrails (SSRF, tunnel-origin lock, per-IP budget, size cap, audit JSONL)
- ✅ No secrets in git (ARCADE_SERVICE_TOKEN in gitignored .env)
- ✅ Rate limiting (express-rate-limit, per-user and per-IP)
- ✅ Idempotency on payment intents
- ✅ Stripe signature verification on webhooks

### 1.6 Integrations
- ✅ Grok/Claude/Fable brains (BYOK wrapper model)
- ✅ fal.ai (image gen) — generate.mjs, one-shot gates
- ✅ Jina Reader / Firecrawl / bundled SSRF scraper (AURA ingest)
- ✅ DexScreener (market data), Helius RPC (Solana), Jupiter DEX
- ✅ MoonPay (PayBox agent wallet)
- ✅ Stripe (checkout + webhooks)
- ✅ Telegram bot (chat + aura)
- ✅ MCP unified (tools + callTool handlers)
- ✅ NewsAPI, DEX Screener (research workflows)
- ✅ GitHub Pages API (publish)
- ✅ DALL-E 3 (image gen for workflows)
- ✅ Chart.js (analytics, optional)
- ✅ EmailJS (email alerts, optional)

---

## 2. WHAT IS NOT DONE (gaps & open items)

### 2.1 Critical gaps (blockers for shipping) — CORRECTED 2026-11-03

> Verification pass: several items previously listed as gaps are actually DONE. Corrected below.

1. **PIKADON as PayBox gateway** — ✅ DONE. `paybox-routes.js` calls `pikadon.review(b)` on POST /tip (FAIL→403, WARN→log+continue, PASS→proceed) and a basic field/amount review on /agent-tip. Status: DONE.
2. **zerox_scan tool** — ✅ DONE. `zerox-scan.js` (DexScreener primary + Helius RPC fallback, loud fail on error) is wired as GET /api/zerox/scan in server-production.js. Status: DONE.
3. **PayBox guard rebuild** — ✅ DONE. `paybox-guard.js` is the corrected version: 5-layer gate (disabled by default, per-call cap, daily budget, approval threshold, ledger), READ_ONLY_TOOLS vs GATED_TOOLS sets, Paybox MCP (pbx_live_* key, JSON-RPC). Status: DONE (enabled flag stays false until owner opts in).
4. **aura_stats endpoint** — ✅ DONE (endpoint). `aura-brain.js` has stats() (boxes, chunks, dataDir, freePerDay, adapters) exposed at GET /api/aura-brain. Status: endpoint DONE; dashboard widget still not wired (frontend gap).
5. **NFT economics** — ❌ STILL OPEN. Pages exist (nft-collection.html, collectibles-nft.html); no economics. Needs spec (benefits, multiplier, priority) before building.
6. **Plots (2D-world land)** — ❌ STILL OPEN. Do not exist yet. Net new. Fee-pool payout formula needs spec + owner sign-off (MASTER-PROMPT-ECONOMY Deliverable 1).
7. **Firebase auth real integration** — ❌ STILL OPEN. server/index.js (SHADDAI-MASTER) uses stubs (random userId). Need real Firebase admin. (Note: server-production.js uses softAuth with JWT/Firebase bearer.)
8. **Database persistence** — ❌ STILL OPEN. In-memory SQLite/JS objects; needs PostgreSQL + Redis for production scale.
9. **Mobile responsiveness** — ❌ STILL OPEN. Most games have 0 touch handlers; dashboard desktop-only. Per-game work needed.
10. **Cross-realm sync (2D↔3D)** — 🟡 PARTIAL. Shared Sparks ledger unified (shaddai.sparks). Cloud push/pull in 3D host still pending.
11. **aura_stats dashboard widget** — ❌ STILL OPEN. Endpoint exists; frontend widget not wired.

### 2.2 High-value open items (owner decisions needed)
- **Founders programme numbers** — price per bracket, what they get, refund policy, cap permanence. (FLYWHEEL.md §founders)
- **Sparks↔USD rate for the 3% tax bridge** — no exchange rate exists anywhere; every catalog item priced in Sparks OR USD, never both. (THURSDAY-HANDOFF #4)
- **NFT benefits spec** — multiplier on payout? priority on plots? (MASTER-PROMPT-ECONOMY Deliverable 1 item 6)
- **Securities/compliance review** — fee-pool payouts, NFT revenue share, founders structure all need legal review if they imply returns. (FLYWHEEL.md "one line you must not cross")
- **SHADDAI coin conversion path** — Sparks→coin path undefined; must state what is NOT promised.
- **Spec contradiction** — HALL-PHASE1-SPEC puts shaddai-games wrapping in Phase 2; implementation shipped. Needs owner ruling. (THURSDAY-HANDOFF #10)
- **Booth pack** — main repo needs booth_bar/booth_verdict in EVENT_SCENES + GROQ_API_KEY set. QUILL copy sign-off outstanding. (THURSDAY-HANDOFF #11)
- **Cross-service auth** — POST /api/groq mounted with rate limits but no auth, falls back to server's GROQ_API_KEY, skips enforceCredits. (THURSDAY-HANDOFF #3)

### 2.3 Medium-value open items
- 3D agent rigs: only idle/run/walk clips; missing combat, dodge, hit, sit, mount, swim, crouch, spell cast, fishing cast/reel, emotes. (OPUS-AUDIT-BRIEF)
- 7 council GLBs ~9 MB, need lazy-loading + LODs for FPS.
- Three.js from CDN needs self-hosting with fallback (done in 3D but verify).
- Colosseum: interchangeable floors not walkable/playable; trailer look (dragon PvP arena, spark pit, fighters with powers) TODO; events/signup/brackets/wagers TODO; grand hall lobby connects all around TODO.
- Hover ships (vehicles) + cockpit interior + first-person view + boost TODO (needs owner art).
- Hover park site selection + host wiring TODO.
- Bots: 6 of 10 roster bots are recolours; need owner refs for new bodies.
- Unified Brain: provider chain fix (Groq 404, HF routing), citations, merge 3D + Classic views. (OPUS-AUDIT-BRIEF #7)
- Performance: instance the ~2,000 unnamed meshes, terrain chunk merge, 46 lights budget, shadow cadence, texture KTX2 audit, dispose on realm exit.
- Mobile: look-sensitivity, haptic/UI scale, landscape check, mobile quality default (LOW), performance toggle, PWA install, WebXR/AR later.
- Interior law: real door + interior + colliders per enterable; E-portals to sized-correct instances.
- Collider + scale laws: walls ≥12m, doors 2.2×1.2m, GLB ≤1.2MB.
- Skate world: wire skate.html into city as arcade building door; sparks entry fees; 3D skatepark later.
- Model-forge for players: dashboard flow → user describes operative → gates → body + clips → their grok bot wears it → fights. BYOK wrapper.
- Economy: one Sparks ledger (done); wager pools; cosmetic market; x402/wallets; plots/ad-space; music submissions (in-game radio); art in turtle museum; NFT-of-month; agent classes (teach/learn); token/staking — all on foundation.
- NFT surfaces: nft-collection.html, collectibles-nft.html pages exist; economics do not.
- Badge system: 40/52 lessons still need Quill rewrite; badge smart contract deploy pending.

### 2.4 Low-value / parked
- AR idea: see your bot in your room (phone/WebXR) — parked.
- Geospatial/atmosphere rendering study (three-geospatial, three-grass-demo) — parked.
- Fishing polish: rod + cast + bite + tension UI in 3D, fish stand, tackle shop, catch card, lure items.
- Loading slideshow art replacement (HF FLUX generic → owner's reference-correct agent art).

---

## 3. HOW IT WORKS (architecture)

### 3.1 Three layers
```
┌─────────────────────────────────────────────────────┐
│  LAYER 1 — DASHBOARD (Command Deck)                 │
│  HQ. 7 agents. Run tasks, earn, build.              │
├─────────────────────────────────────────────────────┤
│  LAYER 2 — 2D PIXEL WORLD (City & Dark Realm)      │
│  Walk the city. Own an office. Siege the dragon.    │
├─────────────────────────────────────────────────────┤
│  LAYER 3 — 3D WORLD (Pro Only)                      │
│  Agent has a 3D body. Founders' Row.               │
└─────────────────────────────────────────────────────┘
```
One identity + one Sparks ledger + portals between 2D/3D/dashboard. Alignment rule: any new feature must touch at least two of {dashboard, 2D, 3D} or it doesn't ship.

### 3.2 Dashboard
- Entry: `/enter.html` (forge archetype cards) → `/forge-gallery.html` (3D viewer)
- Simple Mode: wheel (GAMES, TOOLS, MEDIA, etc.)
- Tools tab: agent status, MCP status, media engine, capture rail
- Office view: per-agent rooms (VISION — 7 rooms, each a themed front door to existing brain)
- Agent Forge: user creates an agent (name, archetype, skills, MD files, personality) → callable from dashboard + autopilot using user's own Grok/LLM subscription (BYOK). Registry extends /api/operatives.

### 3.3 Backend (shaddai-consultancy)
- `backend/server-production.js` — main server (mounts all routes)
- `backend/economy-service.js` + `stripe-webhook.js` + `work-sessions.js` + `services/reward-engine.js` + `games-routes.js` — Sparks ledger
- `backend/x402-*` — micropayments (routes, agent-routes, ledger-routes, security, ledger)
- `backend/paybox-routes.js` + `paybox-guard.js` + `lib/paybox-settle.js` — agent wallet
- `backend/bazaar-routes.js` — resale marketplace
- `backend/aura-brain.js` + `aura-brain-routes.js` + `lib/web-scrape.js` — boxed knowledge
- `backend/media-engine/` — vendored cobalt (AGPL-3.0, rebranded)
- `backend/media-routes.js` + `capture-routes.js` — media + capture rail
- `backend/telegram-bot.js` — Telegram integration
- `backend/agent-engine.js` — agent brains
- `backend/zerox-scan.js`, `tools-nexus.js`, `tools-turtle.js`, `tools-pikadon.js` — agent tools
- `backend/mcp-endpoints/` + `shaddai-mcp/mcp-unified.js` — MCP unified
- `backend/aura-warmer.js` — AURA warmup
- `core/tiers.js` — tier config (Free/Pro/Team)
- `SHADDAI-MASTER/server/index.js` — v58.88 unified backend (auth + billing + agent routing, port 3000, stubs)

### 3.4 APIs (key endpoints)
- Auth: POST /auth/signup, /auth/login, GET /auth/verify
- Billing: GET /billing/usage, /billing/usage/history, POST /billing/usage/track, POST /billing/tier
- Payments: POST /api/stripe/create-payment-intent, POST /webhooks/stripe, /api/paybox/tip, /api/paybox/agent-tip, /api/paybox/tip-link
- Jobs: POST /jobs/post, GET /jobs/list, GET /jobs/{id}, POST /jobs/{id}/bid, GET /earnings/{agent}, POST /earnings/add, POST /payout/request, GET /payout/history
- Agents: /api/agents, /api/operatives, /api/forge/upload
- Economy: /api/economy (balance, inventory, catalog/purchase, grant, spend), /api/x402/*, /api/bazaar/*
- AURA brain: /api/aura-brain/ingest, /api/aura-brain/boxes, /api/aura-brain/search
- Media: /api/media/fetch, /api/media/dl, /api/capture/status, /api/capture/run
- MCP: /api/mcp/status, /api/mcp/tools, tool call handlers
- Skills: POST /skill/{name}, POST /chat, POST /search, POST /workflow, POST /collab
- Signals: POST /signal/telegram, /signal/discord
- Zerox: /api/zerox/scan (VISION)
- Pikadon: pikadon_review middleware (PARTIAL)

### 3.5 Consultancy connections
- Brains: Grok (BYOK), Claude, Fable — user's own subscription, encrypted at rest, per-user isolation
- Image gen: fal.ai (FLUX, Rodin, Tripo, Meshy) — one-shot gates, canary first
- Scraping: Jina Reader → Firecrawl → bundled SSRF scraper
- Market data: DexScreener, Helius RPC, Jupiter DEX
- Payments: Stripe (checkout), MoonPay PayBox (agent wallet), x402 (micropayments)
- Comms: Telegram bot, EmailJS, webhooks
- Storage: localStorage (browser) + PostgreSQL (usage/tiers) + Redis (rate limits) + x402 ledger JSON

---

## 4. ECONOMY: SPARKS, SHADDAI COIN, ASIMOV TOKEN, NFTS

### 4.1 Sparks (the main currency)
- **Fixed: 1 Spark = $1 USD. Never floats.** (FLYWHEEL.md)
- Sources: Stripe purchase (round-up), job completion, siege rewards, work sessions, check-in, class completion, teaching, stall sale, race placement, culture (art sold, radio spin, hired to dress building, exhibit cut)
- Sinks: rent, tuition, Forge install, pit/race entry, stall lease, plot claim, plot boost lock (1.0-1.5x), cosmetics/kits, culture (buy art, hire agent, unlock radio slot, submit to TURTLE wing, studio rent)
- Rule: sinks ≥ print over a normal week. If print wins, raise rent/entry. Never add a cash-out.
- Closed-loop, one-way. No cash-out API may ever be added. (DOC_SPARKS.md)
- Dual layer (later): Soft = SPARKS (play). Hard (optional future) = scarce token/partner rail for governance/cosmetics/claim rights, kept OFF the rent pipe. Gameplay fuel is not an investment object.

### 4.2 Shaddai coin (SHADDAI)
- Separate, later, explicitly speculative asset. (MASTER-PROMPT-ECONOMY)
- Conversion path from Sparks undefined — must be specified. Must state what is NOT promised.
- Do not blur Sparks (fixed $1) with Shaddai coin (speculative).

### 4.3 ASIMOV token (the user's launched token)
- **What it is:** A token paired with NVDAx (NVIDIA stock token on Backed Finance). The site is a token paired with NVDAx, so nothing may imply NVIDIA's backing. (ASIMOV_FULL_GAME_PLAN.md)
- **Rewards:** "NVIDIA rewards" — unverified. Could be NVDAx dividends, pool fees, or something else. Check Backed Finance's current terms for how NVDAx handles dividends. Do not assume there's a rewards stream to spend. (ASIMOV_GAME_HANDOFF.md)
- **Tax:** 3% buy and sell (user stated).
- **Cosmetics unlock:** Holding $ASIMOV or NVDAx unlocks cosmetics (skins, gold cat announcer). Read-only balance check, no fighting advantage, nothing spent. (ASIMOV_GAME_HANDOFF.md)
- **Integration idea (user's):** Add an in-game "ASIMOV / NVIDIA rewards center" with games and other things as a bonus to $sparks or $Shaddai. The 3% tax revenue bridges into Sparks rewards for players.
- **Compliance note:** The 3% tax is real revenue. If it funds player rewards, that's a revenue-share-like flow. Must be structured as "work performed" (gameplay rewards) not "holding returns" to stay on the right side of the compliance line. (FLYWHEEL.md "one line you must not cross")

### 4.4 NFTs
- **Current state:** Pages exist (`nft-collection.html`, `collectibles-nft.html`). Economics do not. (FLYWHEEL.md)
- **Badge system:** 5 tiers (Prospect→Grandmaster) minted as MCP smart contract transactions with IPFS hash of exam answers. Agent council witnesses. (SHADDAI_BADGE_SYSTEM.md)
- **Art NFT:** "a frame, not a cash-out." Art is an inventory item, placeable, traded for SPARKS in-world. Later optional: NFT flag meaning "this copy may hang on-chain / in a museum listing." Provenance + brag. Selling it never converts SPARKS→USDC. Only mint what hung in TURTLE or won a radio week. (DOC_SPARKS.md)
- **NFT benefits:** Unspecified. Needs spec: multiplier on payout? priority on plots? (MASTER-PROMPT-ECONOMY Deliverable 1 item 6)
- **Rule:** No "expected APY", no projections, no "earn X%" copy anywhere. Payout formula = share of fees actually collected, computed after the fact. If pool empty, plots pay zero and UI says so plainly.

### 4.5 Plots (2D-world land) — net new
- Do not exist yet. Needs full spec before building:
  1. Round-up: what rounds (Stripe only? crypto-in too?), to what increment, opt-in/out, what user sees.
  2. Sparks: confirm $1 fixed, where ledger lives, fractional Spark handling.
  3. Plots: how many (fixed supply?), cost in Sparks, how to buy, resellable?, unsold plots.
  4. Fee pool: which fees feed it (name routes), what %, how often settles, where stored for audit.
  5. Payout: formula in full. Given pool P over period T and N plots, what does one plot receive? Worked example at 10 / 1,000 / 10,000 users.
  6. NFT benefits: specific grants (multiplier? priority?).
  7. SHADDAI coin: conversion path + explicit "not promised" statement.
  8. Failure modes: empty pool, refund of purchase whose round-up already paid out, plot supply sells out.
- Owner sign-off required before building.

### 4.6 Compliance line (the one you must not cross)
Selling something for money that pays its holder a share of the platform's revenue — money they did not work for — is an investment contract in substance, whatever the wrapper (NFT, plot, building, coin, "rev share tier"). The name does not matter; the cash flow does.

Fix: make a plot productive rather than passive. Holder earns because their agent works, hosts, or creates from it — not because they hold it. Keep land economy, reason to buy, scarcity, burn-and-buyback. Only the return source changes (work performed), and you're on solid ground.

If passive platform revenue share is wanted anyway: stop and talk to a securities lawyer first.

---

## 5. THE ASIMOV / NVIDIA REWARDS CENTER (user's idea)

### 5.1 Concept
An in-game center (a building/venue in the 2D city, with a 3D counterpart) where:
- Players play games (arcade, tactics, skate, etc.) and earn Sparks or Shaddai coin as rewards.
- The reward pool is funded by the ASIMOV token's 3% buy/sell tax (which generates "NVIDIA rewards" via the NVDAx pairing).
- Holding $ASIMOV or NVDAx unlocks cosmetics (read-only balance check, no fighting advantage, nothing spent).

### 5.2 Why it fits
- Sparks are the single currency (1 Spark = $1). A rewards center that pays Sparks is just another Sparks source — already in the closed-loop model.
- Games already have Sparks entry fees (arcade score bridge). Adding rewards makes the loop: pay Sparks to enter → play → earn Sparks back (net from the tax pool). This is gameplay reward, not holding return.
- The ASIMOV token tax is external revenue that enters the system as a Sparks grant pool. Structured as "work performed" (playing games), not "holding returns."

### 5.3 What needs to happen
1. **Verify NVDAx rewards** — confirm what "NVIDIA rewards" actually means (dividends? pool fees?). Check Backed Finance terms. Do not assume a rewards stream exists. (ASIMOV_GAME_HANDOFF.md)
2. **Define the bridge** — how does 3% tax revenue become a Sparks pool? On-chain listener → treasury → Sparks credit. Needs NEXUS + ZEROX + PIKADON.
3. **Build the center** — a venue in the 2D city (and optionally 3D) with game entry, reward payout, leaderboard, cosmetics unlock.
4. **Cosmetics unlock** — read-only balance check of $ASIMOV/NVDAx holdings → unlock skins/gold cat announcer. No spend, no fighting advantage.
5. **Compliance** — ensure reward framing is "gameplay reward" not "investment return." PIKADON review required before launch.

### 5.4 Open questions for owner
- Is the NVDAx rewards stream real and claimable? (Unverified)
- What % of the tax pool funds in-game rewards vs. platform treasury?
- Which games qualify for rewards? All arcade games or a subset?
- Is Shaddai coin (not Sparks) ever paid out, or only Sparks?
- Cosmetic unlock threshold (min $ASIMOV/NVDAx balance)?

---

## 6. MASTER PLAN FOR OPUS 5.5 (build order)

Opus 5.5 executes Thursday. Budget: $100 fal hard cap, 6 HF keys, 20d Claude Pro. Rule of rules: canary first (one model per family, verified), then batch. Concept-gate before 3D. A model fails twice = the prompt is wrong — redesign the prompt, never re-roll. Reuse: 18 terrain textures, existing GLB pack, forge chars (already generated — finish/ship, never regenerate).

### Phase 0 — Read & align (Opus, before any code)
- Read `docs/MASTER-PROMPT.md`, `docs/GAMEPLAY-EXPANSION-20261002.md`, `docs/QA-PROCESS.md`, `docs/RIG-AUDIT.md`, `docs/JOURNEY-LOG.md`, `docs/RACE-REFERENCES.md`, `docs/UNIFIED-BRAIN-DESIGN.md`.
- Read this master plan (SHADDAI_MASTER_PLAN_OPUS55.md).
- Read `shaddai-consultancy/docs/MASTER-PLAN.md` (ground truth) and `shaddai-consultancy/docs/final/FLYWHEEL.md`.
- Read `shaddai-consultancy/docs/OPUS-AUDIT-BRIEF.md` and `shaddai-consultancy/docs/MASTER-TASKBOARD.md`.
- Confirm the "ready for Opus" checklist (§2 of OPUS-AUDIT-BRIEF) is green.

### Phase 1 — Cross-system regressions & collision (Opus, code-only, zero fal)
1. Stairs, realm hazards (strict wedge membership), passive/Void fight mode, riders seated in cars (rider tilt sign), hover-car slope tilt, race modes + difficulty + hit immunity, districts, footprints, loading slideshow.
2. Read diffs, run all tests, take QA shots, compare against baseline, fix anything worse.
3. Collision probe: invisible walls / walk-through at each realm hub, building entrances, stairs, castle, Colosseum, bridges. Fix collider vs visual mismatches.
4. Performance: profile draw calls, triangles, texture memory, GLB load sizes (7 council GLBs ~9 MB, lazy-load), three.js self-hosted with fallback, quality ladder, FPS. Budgets: 60 fps, <80 draw calls where possible. Keep boot fast.
5. Instance the ~2,000 unnamed meshes, terrain chunk merge, 46 lights budget, shadow cadence, texture KTX2 audit, dispose on realm exit.

### Phase 2 — Rigging & mechanics (Opus + Blender, one heavy job at a time)
1. Shared humanoid combat/dodge/hit/sit/mount clips; mount sockets (bull, gorilla, mammoth, hawk); dragons for Siege Day; boat/sub hulls; car pivots; castle doors.
2. Verify with loader tests + QA shots.
3. Missing clips: death, directional hit reactions, swim, crouch walk, spell cast, fishing cast/reel, mount/dismount, emotes; Zombie set for skeleton enemies; dodge-roll with i-frames; hit markers per ride type.

### Phase 3 — Gameplay completion
1. Colosseum lobby, vending, dynamic terrain, seating, spectating, modes; Navi controls + MODES toggles; NPCs, missions, quest chains; friend bots with gifts; fishing/farm/crafting loop; taming wired to Academy; gear UI for masks/clothing; castle valley with skeleton homes + purple lava; Siege Day scaffold.
2. Tactics engine + colosseum wiring + skate building door.
3. Skate world: wire skate.html into city as arcade building door; sparks entry fees; 3D skatepark later (same engine).
4. Model-forge for players: dashboard flow → user describes operative → gates → body + clips → grok bot wears it → fights. BYOK wrapper.

### Phase 4 — Look & polish (2D direction: 2.5D, NOT perspective 3D)
1. Building exteriors: multi-tile facades + signage + night-lit windows, per-region style.
2. Interiors: real rooms for every shop/office/forge — themed floor/wall sets, furniture, NPC shopkeeper with dialog, counter UI.
3. Items: crisp icon pass (weapons/tools/fishing); fishing = cast/reel timing minigame.
4. Characters: operative roster sprites + walk/attack frames + COSMETIC OVERLAY layer (hats/armor/tints) — that overlay IS the cosmetics marketplace hook.
5. Agentic glue: agents as walking NPCs, quest dialogs, agent-run shops, in-world chat.
6. Atmosphere: parallax starfield/nebula/fog, SHADDAI monument at origin, agent aura/bloom, skill chips, ambient particles, grid pulse, light shafts, color grading. Delta-time movement, camera look-ahead, run (Shift), footstep bob, lean on turns.

### Phase 5 — Economy & legal safety (ZEROX + PIKADON + QUILL)
1. **Spec first:** Write `docs/SPEC-economy.md` with concrete numbers/formulas for round-up, Sparks, plots, fee pool, payout, NFT benefits, Shaddai coin conversion, failure modes. Get owner sign-off.
2. **Compliance review:** PIKADON reviews fee-pool payouts, NFT revenue share, founders structure for securities/gambling/MLM exposure. Flag risks, propose options. Do not decide.
3. **Plots:** Build 2D-world plots (net new) with fee-pool payout (share of collected fees, computed after the fact, never promised rate).
4. **NFT benefits spec:** Define what holding an NFT grants (multiplier? priority?). Then implement badge NFT minting (5 tiers) + art NFT "frame, not cash-out."
5. **Founders programme:** Fill in numbers (price per bracket, what they get, refund policy, cap permanence).
6. **ASIMOV/NVIDIA rewards center:** Verify NVDAx rewards stream; define bridge (3% tax → Sparks pool); build center venue; cosmetic unlock via read-only balance check. PIKADON review before launch.
7. **Sparks↔USD rate:** Resolve the missing exchange rate for the 3% tax bridge (THURSDAY-HANDOFF #4).
8. **PayBox guard rebuild:** Connect Paybox MCP, list real tools, rebuild guard against actual shape. Re-enable.
9. **zerox_scan tool:** Live DexScreener fetch → normalized JSON.
10. **aura_stats dashboard widget:** Surface on dashboard.
11. **PIKADON as PayBox gateway:** Wire pikadon_review → FAIL/WARN/PASS → reject/allow.
12. **Firebase auth real integration:** Replace stubs with Firebase admin.
13. **Database persistence:** Replace in-memory with PostgreSQL + Redis.

### Phase 6 — Cross-realm sync & mobile
1. Shared backend profile: sparks + inventory + name sync between 2D and 3D (cloud push/pull in 3D host).
2. Portals: 2D city door ↔ 3D plaza; 2D beach ↔ Crystal Sea; per-realm equivalents.
3. Mobile: on-screen control surface (thumb stick + action buttons) for WASD games; 44px tap targets for pointer games; look-sensitivity, haptic/UI scale, landscape check, mobile quality default (LOW), performance toggle, PWA install.

### Phase 7 — Security audit (PIKADON, at the very end, once)
1. Grok/LLM keys: encrypted at rest, per-user vault, zero cross-session leakage.
2. /api/operatives + forge endpoints: authz per owner, no IDOR, rate-limited.
3. fal keys: server-side only, rotate runbook, never in client bundles/git.
4. Cloud profile sync: one identity per account (email/wallet/Google merge check), no cross-user data bleed.
5. No secrets in git history; no PII in agent ledger logs.
6. Post /api/groq auth + enforceCredits fix.

### Phase 8 — Release
1. All node tests green (`tools/tests/*.test.cjs`).
2. Headless smoke (`__realmHomes`, `WorldBots`, `WorldSit`, metro station registered).
3. One human browser pass (Navi, homes, colosseum, hoverskate).
4. Perf HUD `?perf=1` numbers on owner's laptop.
5. Push `feat/world3d`, sync Shaddai-Beta `site/`, merge to main (fast-forward possible, 91+ commits). Render auto-deploys main and Beta master.
6. Write `docs/OPUS-AUDIT-REPORT.md` listing what changed, what was verified (how), what is still open, next 10 items.

### Phase W — World + Forge finish (owner order 2026-11-05)
Targets: `shaddai-backup.onrender.com/forge-demo.html` (finish the models and the flow) and `/SHADDAI-WORLD-3D.html` (loading, lag, loading screen, character select, side popups, mode buttons, hide buttons, nothing in the way, removable help notices, smooth Navi, mounts + hoverboard + hover moves fully working). Source: `Shaddai-3d` (IzzoSol/Shaddai), branch `polish/world-finish-p1`, tag `pre-world-polish-p1-20261105`. Plan hub: `plan-hub/index.html` (design-studio diagrams + economy blueprint + 3D maps, merged).

**Measured on live (headless SwiftShader, 2026-11-05):** 165 s to playable, 825 requests, ~30 MB, heap 411 MB. Console: shader compile failure (`'instanceMatrix' : undeclared identifier`), `ZEROX.glb` (12.9 MB) dropped mid-download (QUIC error).

Done (branch `polish/world-finish-p1`, not yet deployed):
1. ✅ Shader fix: the dragon and VFX decal ShaderMaterials guard `instanceMatrix` with `USE_INSTANCING`. Boot bundles rebuilt (`node tools/build-dist.cjs --check` clean).
2. ✅ F2 = hide all UI: session-only, restores exactly what was showing, keeps opened panels (Navi, dossier, districts), and keeps notices hidden while off. Toast confirms; `?hideui=0` disables it. Added to the controls strip.
3. ✅ Key conflict: `\` toggled fight/passive mode AND placed a campfire. Now `\` = passive/fight (matches Navi and the touch buttons) and Shift+`\` = campfire.
4. ✅ Forge demo, real bodies: the Body step offers the 7 council GLBs (the bodies the world can wear, `VALID_MODELS`). The chosen body builds as a skinned hologram, materialises into its real textures and idles. The field bot is your real body, walking while it works. Verified headless: SHADDAI and NEXUS load, build and materialise.
5. ✅ Forge demo, flow end: "Enter Shaddai World" registers the operative via `POST /api/operatives` (owner set from the session, model = chosen body), then opens the world. If the server is unreachable it says so and saves on the device. Verified headless end to end (Bind → Body → License → Labor → PayBox 100 Sparks → Enter).
6. ✅ PIKADON: `POST /api/operatives` now accepts only the creative fields. Before this, a client `id` could overwrite another user's record, and economy/stats/inventory/tokenId were client-settable. Test: `tools/tests/operatives-route.redteam.cjs` (9/9).
7. ✅ Side popup: the Dragon Shards tracker covered the right side permanently. It is now a one-line chip ("DRAGON SHARDS 0/8 ▸") that opens on click (remembered), peeks open for 6 s on a mission briefing or a shard win, and no longer rebuilds its DOM every 2 s. The award toast said "/7" while the tracker counted 8; it now uses the real count.
8. ✅ Verified in-game on the local build (headless): 0 shader errors (live had 1); the shards chip is 31 px tall and opens to the full list; F2 hides the crosshair, mode pill, Navi button, key button, chat panel, shards chip and the HP/stamina layer, shows the toast, and a second F2 restores the same set.

9. ✅ One dragon per realm, each its own: the dark forest shared "thorn" with the meadow (two Verdant Shards). It now has the BLIGHT dragon (obsidian + crimson rot breath, Blight Shard). Reach tuned so its strafe lands and stays dodgeable. Dragon suites 50/50, with a new check that no two realms share an element.
10. ✅ Underground Bazaar v02 (owner picks 2026-11-05: capstone centrepiece, glow gap + 6 glass oculi, cinematic ride). Blender kit K32 rebuilt headless (`shaddai_bazaar_city_v02.glb`, v01 kept). The pyramid is truncated so its 14.4 m gold top step is flush with the street; a 5 m street slab stays solid; a funnel under it opens into the cavern ceiling (≥3.5 m clearance to every pyramid step, checked per step). Street openings: a 14 m gap round the capstone with 4 diagonal gold bridges and railings, plus 6 walk-on glass oculi between the roads. The capstone shrine replaces the marketplace fountain. Lift: a glass car on an inclined rail down the east face's step corners to a new arrival platform; ~12 s cinematic (street dive, cut under the ceiling opening, wide cavern reveal, settle), E/Esc/click skips. The bazaar is ON by default again (`?bazaar=0` off). Terrain supports up to 8 openings (`setHoles`). Fixed on the way: `USE_M` was inside a comment, so the old cavern-lift E check compared against NaN. Verified headless: all hooks load, 7 openings, fountain hidden, plaza floor opened, ride frames at 25/50/75/97 %, player lands on the cavern floor.

Open, in order:
0. Bazaar polish (owner eyes): the cavern is lit by the surface sun as well as its own lights, so it reads washed out; the bridges need a close look in a real browser; the cinematic camera keys may want art direction.
1. Lag, by measured priority: shadow casting only near the player, hide realm towns beyond 1.2 km and titans beyond 2.5 km, merge static meshes per material (`world-static-batch.js` / `world-merge.js`), lazy-load the council GLBs with LODs (§2.3). Measure before and after each change with `tools/_ui-probe.cjs` on a machine with ≥1.5 GB free (this laptop kept dropping to ~360 MB free with other apps open).
2. `ZEROX.glb` 12.9 MB: the only council body without meshopt + webp (the others are 0.7–5 MB). Run the same pipeline as NEXUS/ORACLE/QUILL. `ZEROX_packed_old.glb` (4.8 MB) exists and was set aside once, so the owner checks the look before it replaces the live file.
3. Character select: the cards are 2D portraits. Show the real bodies (one shared renderer, small turntables).
4. In-game verification still owed (the world could not run headless at session time): O hoverboard + tricks + wall-ride, I mounts & travel, Y Navi open/close smoothing, F2 in every realm and interior.
6. Spawn time: headless, the world was playable at 111 s but the Source Temple spawn took ~750 s. Software rendering exaggerates this, but it is the slowest step measured; profile it on a real GPU first.
7. `rarity` on `POST /api/operatives` is still client-relayed (forge.html passes what `/api/forge` returned). Move it server-side (Phase 7 item 2).

---

## 7. OPEN DECISIONS (owner must decide)

1. Founders programme numbers (price per bracket, rewards, refund policy, cap permanence).
2. NFT benefits (multiplier? priority?).
3. Passive vs. productive plots (compliance line).
4. ASIMOV/NVDAx rewards stream verification + % allocation to in-game rewards.
5. Sparks↔USD rate for the 3% tax bridge.
6. SHADDAI coin conversion path + "not promised" statement.
7. Spec contradiction: HALL-PHASE1-SPEC Phase 2 vs. shipped implementation.
8. Booth pack: booth_bar/booth_verdict in EVENT_SCENES + GROQ_API_KEY + QUILL copy sign-off.
9. Cross-service auth: POST /api/groq auth + enforceCredits.
10. Whether to add Stripe alongside or replace with dynamix.xyz (payment architecture decision — currently recommended Option B: replace Stripe with dynamix.xyz, 4-6 hours).

---

## 8. RISKS & COMPLIANCE

- **Securities:** Fee-pool payouts, NFT revenue share, founders structure must not promise returns. Structure as "work performed" rewards. If passive revenue share wanted, needs securities lawyer.
- **Gambling:** Wager pools (Colosseum, Sparks betting) may trigger gambling regulation. PIKADON must review before launch.
- **MLM:** Referral structures must not resemble pyramid schemes. Review.
- **ASIMOV token:** 3% tax is real revenue. If it funds player rewards, frame as gameplay reward, not investment return. Verify NVDAx rewards stream exists before promising.
- **NFTs:** "Art NFT = a frame, not a cash-out." Selling NFT never converts SPARKS→USDC. Only mint what hung in TURTLE or won a radio week.
- **Sparks:** Closed-loop, one-way, no cash-out API. Never add a cash-out.
- **PIKADON:** All payment flows must pass pikadon_review before PayBox. Currently PARTIAL — must be wired before launch.

---

## 9. KEY FILES & POINTERS

### Master docs (read first)
- `C:\Users\Brittany\SHADDAI_MASTER_PLAN_OPUS55.md` (this file)
- `C:\Users\Brittany\shaddai-consultancy\docs\MASTER-PLAN.md` (ground truth, overrides older docs)
- `C:\Users\Brittany\shaddai-consultancy\docs\final\FLYWHEEL.md` (how money works)
- `C:\Users\Brittany\shaddai-consultancy\docs\final\GAMES.md` (every game, real controls)
- `C:\Users\Brittany\shaddai-consultancy\docs\final\README.md` (doc index)
- `C:\Users\Brittany\shaddai-consultancy\docs\OPUS-AUDIT-BRIEF.md` (Opus audit brief + ready checklist)
- `C:\Users\Brittany\shaddai-consultancy\docs\MASTER-TASKBOARD.md` (taskboard)
- `C:\Users\Brittany\shaddai-consultancy\docs\MASTER-PROMPT-ECONOMY.md` (economy build brief)
- `C:\Users\Brittany\shaddai-consultancy\docs\SHADDAI_HALL_MASTER_BUILD_BIBLE.md` (HALL build bible)
- `C:\Users\Brittany\shaddai-consultancy\docs\SHADDAI_WORLD_VISION.md` (world vision)
- `C:\Users\Brittany\shaddai-consultancy\docs\SHADDAI_MASTER_BLUEPRINT_2026-08-09.md` (investor blueprint)
- `C:\Users\Brittany\shaddai-consultancy\docs\city-v3\DOC_SPARKS.md` (Sparks law)
- `C:\Users\Brittany\shaddai-consultancy\docs\city-v3\DOC_DASHBOARD.md` (dashboard tiles)
- `C:\Users\Brittany\SHADDAI_v57.77_STATUS.md` (v57.77 status)
- `C:\Users\Brittany\SHADDAI_V58_88_FLAGSHIP_WORKFLOWS.md` (flagship workflows)
- `C:\Users\Brittany\SHADDAI_BADGE_SYSTEM.md` (badge/NFT system)
- `C:\Users\Brittany\SHADDAI_CODE_FOR_CLAUDE.md` (payment architecture review)
- `C:\Users\Brittany\PAYMENT_ARCHITECTURE_DECISION.md` (payment decision)
- `C:\Users\Brittany\OBSIDIAN_ORGANIZATION_STRUCTURE.md` (Obsidian vault plan)
- `C:\Users\Brittany\THURSDAY-HANDOFF.md` (Thursday handoff, open items)
- `C:\Users\Brittany\ASIMOV_GAME_HANDOFF.md` (ASIMOV token / NVIDIA rewards)
- `C:\Users\Brittany\ASIMOV_FULL_GAME_PLAN.md` (ASIMOV game plan)

### ASIMOV token references
- `C:\Users\Brittany\ASIMOV_GAME_HANDOFF.md` §"NVIDIA rewards": decision needed
- `C:\Users\Brittany\ASIMOV_FULL_GAME_PLAN.md` §license/credit (token paired with NVDAx)
- `C:\Users\Brittany\ASIMOV_FINISH_HANDOFF.md` (finish ASIMOV site)

### Backend entry points
- `C:\Users\Brittany\shaddai-consultancy\backend\server-production.js` (main server)
- `C:\Users\Brittany\SHADDAI-MASTER\server\index.js` (v58.88 unified backend, port 3000, stubs)
- `C:\Users\Brittany\SHADDAI-MASTER\core\tiers.js` (tier config)

### Obsidian
- Only Obsidian vault present: `C:\Users\Brittany\Obsidian Vaults\ASIMOV` (ASIMOV story series). No SHADDAI Obsidian vault exists yet — the OBSIDIAN_ORGANIZATION_STRUCTURE.md describes a planned vault that was never created. SHADDAI plans live in the consultancy docs/ and home-root *.md files.

---

## 10. SUMMARY FOR OPUS 5.5

**What's done:** The full 3-layer world foundation, 7 agent brains, Sparks ledger (closed-loop, $1 fixed), Stripe→Sparks, x402, PayBox routes, AURA brain boxes, media engine, capture rail, Telegram bot, MCP unified, 2D world with regions/arcade/fishing/NPC dialogs, 3D world with biomes/GLBs/tactics/swim/seating, hoverboard/boats/roads, performance work, security hardening (Sparks bug fix, PIKADON SSRF, media guardrails), badge system (12/52 lessons), flagship workflows.

**What's not done:** PIKADON as PayBox gateway, zerox_scan, aura_stats widget, PayBox guard rebuild, NFT economics, plots (net new), Firebase auth real integration, DB persistence, mobile responsiveness, cross-realm sync, 3D rig clips, Colosseum polish, hover ships, Unified Brain provider fix, founders programme numbers, ASIMOV/NVDAx rewards bridge, Sparks↔USD rate.

**The big idea (user's):** Bridge the ASIMOV token's 3% buy/sell tax (NVDAx-paired) into an in-game rewards center that pays Sparks or Shaddai coin for gameplay, unlocking cosmetics via read-only balance check. Must be structured as gameplay reward, not holding return, to stay compliant.

**The compliance line:** Never promise returns on holdings. Make plots productive (work performed), not passive. NFTs = provenance + brag, not cash-out. Sparks = closed-loop store credit, never floats, no cash-out API.

**Opus 5.5's job:** Execute Phases 1-8 in order. Read first. Canary before batch. Concept-gate before 3D. Spec before economy code. PIKADON audit last. Write OPUS-AUDIT-REPORT.md at the end.

---
*Prepared by QUILL · SHADDAI Council · 2026-11-03*
*Single source of truth for the Opus 5.5 pass.*
---

# APPENDIX — DEEP INVENTORY (every last thing)

## A1. ALL REPOS & REMOTES (GitHub: IzzoSol / IzzoIzzoIzzo)

| Local folder | GitHub remote | Branch | Purpose |
|---|---|---|---|
| Shaddai | IzzoSol/Shaddai.git | feat/market-intel | Main repo (dirty checkout) |
| Shaddai-3d | IzzoSol/Shaddai.git | fix/bazaar-agents-20261101 | 3D world (feat/world3d) |
| Shaddai-Beta | IzzoSol/Shaddai-Beta.git | fix/policy-honesty-and-catalog-endpoint | Deploy target (Render) |
| Shaddai-consultancy | IzzoSol/Shaddai.git | feat/consultancy-dashboard | Main build (backend + docs) |
| Shaddai-brain | IzzoSol/Shaddai.git | feat/unified-brain | Unified Brain (sparse copy) |
| Shaddai-v1013 | IzzoSol/Shaddai.git | v101.3-polish | v101.3 polish branch |
| Shaddai-city-backend | IzzoSol/Shaddai.git | feat/city-backend | City backend |
| shaddai-mcp-repo | IzzoSol/shaddai-mcp.git | main | MCP + RAG server (7 agent KBs) |
| Shaddai-Royale | IzzoSol/Shaddai-Arcade.git | feat/hall-platform-phase1 | Arcade (blackjack, hall platform) |
| Shaddai-Realms | IzzoIzzoIzzo/Shaddai-Realms.git | master | Realms strategy game |
| asimov-site | IzzoSol/asimov-site.git | feat/polish-round-2 | $ASIMOV token site (private) |
| asimov-trailer | IzzoSol/asimov-trailer.git | main | ASIMOV animated series (private) |
| shaddai-game-forge | IzzoSol/shaddai-game-forge.git | (not checked) | Game forge assets |
| shaddai-design-studio | IzzoSol/shaddai-design-studio.git | (not checked) | Design studio |
| Shaddai-ARVR | (no remote) | master | AR/VR experiments |
| shaddai-hub | (no remote) | (not checked) | Hub |
| shaddai-arena | (not checked) | (not checked) | Arena |
| shaddai-academy | (not checked) | (not checked) | Academy |
| shaddai-n8n | (not checked) | (not checked) | n8n workflows |
| Dreamers-Ecosystem-clone | IzzoIzzoIzzo/Dreamers-Ecosystem.git | master | Dreamers clone |
| Shaddai-AI-IA-Project | (not checked) | (not checked) | AI/IA project |

Shared remote "clipper" -> IzzoSol/Shaddai-Clipper-Feature.git (used by Shaddai, Shaddai-3d, Shaddai-consultancy, Shaddai-brain, Shaddai-v1013, Shaddai-city-backend).

## A2. MCP SERVERS

| Server | Location | Purpose |
|---|---|---|
| aura | mcp-servers/aura | Dependency-free token saver (cache exact/fuzzy, local compute, LLM fallback). MCP server + CLI. Cache in ~/.shaddai-aura. Zero deps, MIT. |
| shaddai-agents | mcp-servers/shaddai-agents | MCP bridge to the 7 council agents: shaddai_ask (quick Q), shaddai_task (agentic), shaddai_list_agents. Ports 8000-8008. |
| shaddai-mcp | shaddai-mcp-repo | RAG + MCP server: mcp-server-rag.js, rag-index.js. 7 agent KBs (kb_shaddai 98KB, kb_zerox 34KB, kb_oracle 63KB, kb_nexus 1.5MB, kb_turtle 5KB, kb_quill 17KB, kb_pikadon 530KB). TF-IDF (idf.json + docs.json per agent). |
| shaddai-mcp (in consultancy) | shaddai-consultancy/shaddai-mcp | lib/eco-telegram.js + MCP unified (mcp-unified.js) with 24 tools, 3 servers, 7 agent KBs. |

## A3. AURA / RAG BRAIN

- AURA: answers recurring prompts for free via local cache (exact + fuzzy), saved skills, deterministic compute (math, units, dates, base64, word count, %, tip, % change, days between). LLM fallback only with --llm and a model key. Auto-picks cheapest capable model. Inspired by AINL (keep model off hot path).
- AURA brain boxes: hall/<owner>/<slug> (shared, readable by all), <office>/<owner>/<slug> (private). Ingest via Jina Reader -> Firecrawl -> bundled SSRF-guarded scraper. ~500-token chunks. SERVE layer: aura_ingest, aura_search, aura_boxes MCP tools. Telegram /learn, /boxes, /ask (answers from caller's boxes first, grounded snippets).
- PIKADON guard: https-only, private/literal-IP/localhost/.local DNS blocked, /api|admin|internal paths blocked, per-box chunk cap. Metered ingest: free N ingests/user/day (AURA_FREE_INGESTS, default 5), then 402 paid rail (x402 Solana USDC). Libretto (Playwright recorder) is VISION/NEXUS-only, never spawned from MCP or Telegram.
- RAG index: per-agent TF-IDF. kb_* folders with docs.json (chunked docs) + idf.json (inverse document frequency). Used by shaddai-mcp and the council agents' RAG search.

## A4. TELEGRAM BOTS & SIGNALS

- telegram-bot.js: long-polling interactive bot. Commands: /start /help /price /rug /ask /learn /boxes /lb /pnl /stats /dist /signals /gm. Reuses FREE DexScreener + rugcheck.xyz APIs. LLM via /api/model/chat for /ask. Token from env (TELEGRAM_BOT_TOKEN). Fail-safe no-op if unset.
- telegram-signals.js: ZEROX signals terminal. Pre-post validation: FDV gates (minFdv, HARD_FDV_CAP_MAX), rug score (RUG_MIN_SCORE 50), holder count (min 100), distribution quality (top 10 < 55%), LP lock (>= 80%), insider/sniper/bundler detection. Risk scoring 0-100, viability scoring 0-100. Call tracking, performance analytics, dead coin analysis, win rate, source scoring, dynamic gates based on historical performance.
- telegram-core.js, telegram-pnl.js, telegram-wallets.js, telegram-news.js, telegram-routes.js.
- Signals pages: /signals.html, /pro-signals.html, /simple-signals.html, /zerox-live-signals.html, /zerox-meta-signals.html. Pro Signals terminal (Pro tier): ZEROX sentiment, RAG brain.
- SIGNAL_QUALITY_SYSTEM_V2: shipped (commits f6940a6, 81c7105, 2806506, ee89275, b1090c0).

## A5. BAZAAR (THE AGORA)

- Real marketplace where users list items, trade skills/services, and request external orders. Buying settles through the x402 SHAD-Credits ledger. 5% marketplace fee (mirrors x402).
- Endpoints: GET /api/bazaar/list?kind=, POST /api/bazaar/list-item, POST /api/bazaar/buy (x402 charge buyer, credit seller), DELETE /api/bazaar/:id, POST /api/bazaar/order-external (queued fulfillment), POST /api/bazaar/purchase, GET /api/bazaar/purchase/:reference.
- resolveItem across bazaar/collectible/forge stores (normalized descriptor: source, id, name, priceCredits, seller, sellable, reason).
- Files: bazaar-routes.js, lib/bazaar-checkout.js, data/bazaar.json, data/collectibles.json, data/forge-state.json, data/bazaar-purchases.json, data/collectible-trades.json.
- UI: bazaar-buy.css, bazaar-buy.js. Dashboard tile "BAZAAR" (currently pointed at /forge-3d.html — needs fix to point at real bazaar).
- COLOSSEUM-AND-DRAGONS-SPEC: bazaar integration planned.

## A6. GAMEPLAY MODES

| Game | Path | Mobile? | Notes |
|---|---|---|---|
| Dreamers Climb | /games/dreamers-climb/ | partial | Flagship ascent run, 8 radio stations |
| SHADDAI Royale | /games/royale/ | yes (tap) | Blackjack, agent-vs-agent wagering home |
| SHADDAI Realms | /realms/ | partial | Strategy/conquest over realm map |
| Neon Hoops | /games/basketball.html | partial | 4 touch handlers |
| Grid Dodgeball | /games/dodgeball.html | NO | 0 touch handlers |
| Grid Gridiron (football) | /games/football.html | partial | 2 touch handlers |
| SHADDAI Arena (shooter) | /games/shaddai-shooting.html | partial | 3 touch handlers |
| SHADDAI Soccer | /games/shaddai-soccer.html | NO | 0 touch handlers |
| XTO Adventure | /games/xt-adventure.html | NO | 0 touch handlers |
| Tactics | /games/tactics.html | NO | 0 touch handlers, pointer-only |
| Battle Arena | /games/battle-arena.html | NO | 0 touch handlers, pointer-only |
| Skate | /games/skate.html | partial | Sparks entry fees, trick videos |
| Sigil Storm | /games/sigil-storm.html | partial | — |
| Tactics (FFT) | world-tactics.js | NO | Grid battle, CT turn order, bot opponents, pot payouts |
| Castle Siege | (scaffold) | NO | Forest camps -> dragon boss -> loot/sparks. Siege Day dormant until 50 players. |
| Hover skate | world-hoverboards.js | partial | Trick core, battle vs hoverskate, combos, 14/14 tests |
| Hover ships | (TODO) | NO | Needs owner art; cockpit + FPV + boost |
| Hover park | (partial) | NO | 7 rooms, race track, circuits, gates |
| Fishing | world-fishing.js | partial | Cast/reel timing, Void-Pearl 1-in-100 |
| Race | world-race.js | partial | Modes: race/time trial/free ride, AI levels, hit immunity, agentic items |

Most games are NOT mobile-playable (0 touch handlers for dodgeball, soccer, XTO, tactics, battle arena). Fixing mobile = per-game on-screen control surface + 44px tap targets, not global CSS.

## A7. APP-STORE / SCRAP-2D OPTION

- Option A (current decision): Keep 2D as the product. "2D world is the product, 3D is the cinematic showroom." Don't merge codebases. One identity + one Sparks ledger + portals. (MASTER-PLAN.md section 12)
- Option B: Scrap 2D, ship 3D only. Risk: lose the pixel-world moat (interiors, agent NPCs, agentic dialogs, fishing, arcade). Not recommended.
- Option C: Ship 2D to app stores (mobile). Requires per-game mobile controls (not global CSS). Most games need real work.
- Option D: Ship a companion mobile app connecting to the dashboard + Sparks ledger, with 2D world as "lite" mode. Pragmatic.
- Recommendation: Keep 2D as product (per master plan), ship mobile controls per-game (Phase 6), defer app-store submission until mobile verified on a real phone. Consider PWA first, native app second.

## A8. ASIMOV TOKEN (optional, but we have it)

- Chain: Solana. Paired with NVDAx (tokenized NVIDIA share on Backed Finance). Launched on StonkFun.
- Thesis: "To buy the fiction you spend the fact." Meme token, no intrinsic value, not financial advice.
- Rewards: "NVIDIA rewards" — unverified (could be NVDAx dividends, pool fees). Check Backed Finance terms. Contract address posts at launch (not yet live).
- Tax: 3% buy and sell (user stated).
- Cosmetics: holding $ASIMOV or NVDAx unlocks cosmetics (skins, gold cat announcer). Read-only balance check, no fighting advantage, nothing spent.
- Non-affiliation: not affiliated with NVIDIA, Backed Finance, StonkFun, Asimov estate.
- Integration: bridge 3% tax -> in-game Sparks reward pool (gameplay reward, not holding return). Needs NVDAx rewards verification first.

## A9. DIAGRAM / VISUAL HTMLS

- shaddai-consultancy/public/world-map-concept.html — transit concept map (district cells, 2D layout).
- shaddai-consultancy/public/office-workflow-redesign.html — office workflow redesign.
- shaddai-consultancy/public/workflows-builder.html — workflows builder UI.
- shaddai-consultancy/fal-assets/production/map.html — fal asset map.
- SHADDAI-MASTER/shaddai.html — main dashboard (1.5MB single file).
- SHADDAI-MASTER/command-center.html — command center UI.
- SHADDAI-MASTER/login.html — login page.

## A10. 3D VISUAL + PRIVATE REPO

- 3D visual: shaddai-3d-visual.html (three.js, interactive node graph of the SHADDAI architecture). Pushed to the private repo.
- Private repo: IzzoSol/shaddai-master-plan (private). Contains master plan + 3D visual + supporting docs.

---
*Appendix by QUILL · SHADDAI Council · 2026-11-03*
'
---

# DEEP PLANNING — ALL AGENTS (2026-11-03)

Compiled from parallel agent deep-planning outputs. Each section is the raw agent deliverable.

## DP1. SHADDAI — Opus 5.5 Execution Checklist

See full checklist in the master plan §6. Key additions from SHADDAI's review:

- **Contradictory PayBox status:** §2.1 marks "PIKADON as PayBox gateway" as ✅ DONE, but §2.2 and Phase 5 still list it as open. Reconcile before assigning. (Verified: it IS done in paybox-routes.js.)
- **15 dirty repos, 91+ commits, no merge plan:** No rollback/conflict-resolution strategy documented. Risk of catastrophic merge. Add smoke test script to Phase 8.
- **ASIMOV rewards center built on unverified revenue:** NVDAx "NVIDIA rewards" stream unconfirmed. Verify Backed Finance terms before any code.
- **No CI/CD pipeline:** Tests are manual. Add automated gate before 91-commit merge.
- **Mobile testing has no real device:** PWA install and touch handlers need physical phone verification.
- **Missing docs may not exist:** Phase 0 references 12 docs. Verify they exist before starting.
- **No rate-limit on AURA ingest paid rail:** 402 paid rail exists but no per-user spend cap documented. Risk of runaway costs.
- **Single-file 1.5MB dashboard:** No code-splitting or lazy-loading plan. Performance budget may be exceeded on mobile.

## DP2. NEXUS — Rewards Center Technical Spec

**Bridge (3% tax → Sparks pool):** On-chain listener (Helius webhook) → idempotency via tx signature (processed_sigs table, UNIQUE on sig+slot) → treasury ATA (multisig, Squads Protocol, HSM-backed) → `EconomyService.grant(POOL_USER_ID, amount, 'asimov_tax_bridge', sig)`. Treasury reconciliation nightly (alert on drift >0.5%). Convert 1:1 (1 USDC = 1 Spark). No cash-out path added.

**Pool data structure:** `reward_pool {pool_id, balance_sparks BIGINT, updated_at}`, `bridge_ingest_log {sig PK, amount_sparks, kind, ingested_at}`, `play_reward_log {match_id PK, user_id, result, sparks_paid, idempotency_key, paid_at}`. Pool is synthetic user `__asimov_pool__` in economy_accounts.

**Venue:** 2D entry = new building in shaddai.html city layer (pixel-art facade, "ASIMOV Arena" sign). Click → match lobby panel. 3D counterpart optional under asimov-3d/ (lazy-loaded, desktop only). Flow: Lobby → Match (server-authoritative Colyseus) → Result → Sparks credit + leaderboard. Leaderboard top-20 by Sparks earned this week, resets Monday 00:00 UTC.

**Cosmetics unlock (read-only):** Server calls Helius RPC `getTokenAccountsByOwner(wallet, mint)` — never trust client. Thresholds: ≥100 ASIMOV → "Neon Skin"; ≥1000 → "Gold Cat Announcer"; NVDAx holder → "NVDAx Chrome" (US-blocked). On unlock: `EconomyService.grantItem(userId, cosmeticCatalogId, 1, idempotencyKey)`. No fighting advantage.

**Payout formula:** Match completed (any result) +1 Spark (participation). Win +2 (total 3 per win). 3-win streak +1 bonus. Daily cap per user: 20 Sparks from play rewards. Pool floor: if pool < 100 Sparks, rewards pause. Anti-farming: match ≥60s + ≥3 player inputs, server-validated.

**API endpoints:** POST /api/rewards/bridge/ingest (webhook), GET /api/rewards/pool/balance, POST /api/rewards/play/complete, GET /api/rewards/leaderboard, GET /api/rewards/cosmetics/check, POST /api/rewards/cosmetics/unlock.

**Mobile:** 2D venue only on max-width:768px; 3D gated behind matchMedia. Touch controls reuse asimov-fight touch layer. Leaderboard paginated 10/page. Bridge listener server-side only. Cosmetics balance check uses public RPC (read-only, cached 60s).

## DP3. ZEROX — Rewards Bridge Economic Model

**Bridge rate:** 1 Spark = $1.00 USD. Tax revenue converts 1:1. $1 tax = 1 Spark.

**Pool sizing (daily):**
| Scenario | Daily Volume | Tax/Day | Sparks/Day |
|----------|-------------|---------|------------|
| Conservative | $100K | $3,000 | 3,000 |
| Base | $500K | $15,000 | 15,000 |
| Bull | $2M | $60,000 | 60,000 |

Base case: $500K daily volume → 15,000 Sparks/day inflow.

**Payout formula (base case, 10K players/day):** Entry sink 1 Spark × 10,000 = 10,000 out. Win reward 2 Sparks × 4,000 wins = 8,000 in. Leaderboard top-10: 263 in. Daily challenge: 500 in. Total print: ~8,763/day. Other sinks ~6,000/day. Net circulation: −7,237/day (deflationary). Pool change: +6,237/day. Pool cap: 30-day reserve (~263K Sparks). Excess → seasonal tournaments, plot auctions, bonus drops.

**Dynamic adjustment:** If pool < 15-day reserve → reduce win reward to 1.5 Sparks. If pool > 45-day reserve → increase to 2.5 Sparks.

**Founders programme (100 spots):**
| Tier | Spots | Price | Gets |
|------|-------|-------|------|
| Spark | 25 | $49 | Lifetime Pro, founder badge+frame, priority claim on 1 plot, 50 bonus Sparks, name in credits |
| Flame | 25 | $99 | All Spark + priority claim on 3 plots, exclusive cosmetic set, 100 bonus Sparks, beta access |
| Blaze | 50 | $199 | All Flame + priority claim on 5 plots, legendary cosmetic, 250 bonus Sparks, direct feedback channel, early feature access |

Revenue: $13,650 total. Refund: 14-day no-questions. After Pro activation: no refunds. No yield, no revenue share, no staking return.

**Compliance frame:** No passive revenue share on holdings. Tax revenue is platform revenue, not dividend. Sparks distributed only for gameplay activity. Disclaimers: "Sparks are non-transferable game credits. Not securities. No cash-out. Rewards are activity-based prizes, not holding returns."

**Break-even:** Pool self-sustaining when daily tax ≥ daily print. Break-even volume: 8,763 / 0.03 = ~$292K/day ASIMOV volume. Below $292K: pool depletes. Above $500K: pool accumulates.

**Owner decisions needed:** (1) Confirm base volume ($500K) or provide actuals. (2) Approve dynamic payout multipliers (1.5x–2.5x) vs fixed. (3) Approve founders pricing and spot counts. (4) Confirm pool cap target (30-day reserve) and excess-drain mechanism. (5) Verify "NVIDIA rewards" claim — if unverifiable, remove from all marketing.

## DP4. ORACLE — NVDAx Research Brief

**NVDAx (Backed Finance) — Dividend Terms:** Tracker certificate issued by Backed Assets (JE) Limited (Jersey SPV, JFSC-registered), 1:1 backed by real NVDA shares held by regulated custodians. Distributed under Liechtenstein FMA-approved base prospectus (EU Prospectus Regulation), passportable across EEA. Not offered to US persons (Reg S restriction). Holder terms governed by Jersey law.

**Dividend handling:** Dividends are NOT paid as cash. Custodian receives dividend and reinvests into additional NVDA shares, net of 30% US withholding tax. Reflected on-chain as multiplier increase that rebases every holder's balance automatically. No action required. (Verified via xStocks Docs, Kraken FAQ, Token Terminal.)

**Key constraint:** There is NO separable "rewards stream." Dividend value is automatically reinvested into the holder's own position — cannot be extracted, redirected, or pooled. Additionally, NVDAx's US-person exclusion means any game mechanism tying rewards to NVDAx holdings exposes SHADDAI to securities distribution risk if US users served.

**Compliance landscape:** SEC March 2026 interpretive guidance (Release 33-11412) applies Howey test. Activity-based prizes (skill, gameplay, achievements) are less likely to be securities. Holding returns (rewards proportional to token holdings, staking-like yield) are more likely to be investment contracts. Gambling: if prize money derives from participant entry fees → likely gambling. If funded by third-party sponsors → generally lawful. Risk increases where rewards exchangeable for fiat/crypto with market value. MLM: if rewards require recruitment/downline, or early participants profit from later entrants' activity, pyramid concerns arise. Activity-based prize vs. holding return is the critical line.

**Comparable models:** Axie Infinity (SLP) — two-token, SLP earned through gameplay, burned for breeding, emissions ended Jan 2026 due to farming abuse. STEPN (GST/GMT) — move-to-earn, GPS-tracked. Gods Unchained (GODS) — fragments allocate reward pool share based on rank/performance. Common compliance pattern: skill-based eligibility, non-transferable soul-bound in-game credits, geo-blocking, clear T&Cs, no recruitment requirements.

**Recommendations:** (1) Do not use NVDAx dividends as direct reward stream — auto-reinvested, US-restricted. (2) Structure Sparks as activity-based prizes. (3) Make Sparks non-transferable and non-redeemable for cash/crypto. (4) Geo-block US persons. (5) No recruitment/downline mechanics. (6) Engage securities and gaming counsel. (7) Publish clear disclaimers.

**Confidence:** High on NVDAx mechanics and US restriction (verified). Medium on compliance landscape (evolving). Low on MLM-specific analysis (no direct precedent). What would change my mind: legal opinion confirming Sparks are non-securities, or evidence that comparable tax-funded reward pool survived regulatory scrutiny.

## DP5. TURTLE — Rewards Center Venue Spec

**District:** Nexus (cyan tech quarter). Neon-lit arcade facade, holographic NVDAx Chrome trim, ASIMOV token sigil over door.

**Facade (2D, 16px tiles, 48x48 sprite):** obsidian base #0a0e1a, gold signage #e8c45c, emerald energy strips #00ff9c, cyan holographic windows. Night-lit: windows glow cyan pulse (2s loop). Doorway arch with ASIMOV sigil. Reference: world-map-concept.html district cell pattern; office-workflow-redesign.html panel corner brackets.

**Interior (5 zones, top-down 2D):** (1) Lobby — welcome kiosk, daily-cap progress ring, cosmetics preview mannequin. (2) Match Arena — center stage, 2-player match surface, score HUD, countdown timer. (3) Leaderboard Wall — right wall, top-10 Sparks earners, per-player avatar + NVDAx badge. (4) Cosmetics Display — left wall, 3 pedestals (Neon Skin, Gold Cat Announcer, NVDAx Chrome), preview carousel. (5) Pool Status Ticker — bottom strip, scrolling balance/earnings/cap.

**Mobile controls (touch):** Left: virtual thumb stick (movement) — cyan ring, emerald knob. Right: 3 action buttons — A (jump/dash) gold, B (interact) emerald, C (special) cyan. 48px min tap targets, 8px gap. Above stick: pause. Haptic on hit.

**Cosmetics display:** Pedestal = 48x48 sprite, hover → 2x preview with rotation. Unlocked: gold border + emerald check. Locked: desaturated + price in Sparks. Preview modal: 3D turntable (lazy, desktop only), equip button.

**Pool Status Ticker:** Bottom strip, mono font, scrolls: `POOL: 12,450 Sparks · YOU: 340 · DAILY CAP: 500/1000`. Color: pool balance cyan, your earnings gold, cap emerald→red when >80%. Tap → expands to breakdown modal (per-game earnings, cap reset timer).

**3D counterpart (Pro-only, lazy):** Three.js scene, GLB arcade cabinet + neon signage, bloom post-processing. Desktop-only, IntersectionObserver lazy-load, fallback to 2D sprite on mobile/low-end. Camera: isometric 45°, orbit disabled on touch.

**Color palette (SHADDAI canonical):** Obsidian #0a0e1a (base), Gold #e8c45c (accents/CTAs/unlocked), Emerald #00ff9c (energy/success/caps OK), Cyan #5fe0ff (holographic/tech/highlights), Red #ff4d6d (cap warning/sell), Violet #a98bff (ASIMOV token). Motion: 200ms ease transitions, glow pulses 2s, scanline overlay 4% opacity. Typography: Chakra Petch (display), Share Tech Mono (data).

## DP6. PIKADON — Security Review (Severity-Rated)

**1. On-Chain Listener (Helius Webhook) — CRITICAL:**
- [CRITICAL] No webhook signature verification. Fix: verify Helius X-Helius-Signature HMAC (timing-safe compare) before processing.
- [CRITICAL] No idempotency on tx signature. Fix: persist processed signatures in processed_sigs table with UNIQUE on (signature, slot); reject duplicates with 409.
- [HIGH] No replay protection/timestamp freshness. Reject payloads older than 5 min; track last-seen slot.
- [HIGH] SSRF via URL inputs. Pass through assertPublicUrl from ssrf-guard.
- [MEDIUM] Agent dispatch injection. Sanitize task strings (strip control chars, cap length, treat as data).

**2. Treasury Security — CRITICAL:**
- [CRITICAL] Treasury ATA key management unspecified. Fix: multisig (Squads Protocol on Solana) ≥3-of-5 signers; HSM-backed keys (Fireblocks/Turnkey). No hot wallet.
- [HIGH] No balance reconciliation. Nightly job comparing on-chain treasury inflows vs. Sparks granted; alert on mismatch >0.1%.
- [MEDIUM] Treasury address not allowlisted. Hardcode ASIMOV token program ID and treasury ATA; reject anything else.

**3. Sparks Minting Integrity — CRITICAL:**
- [CRITICAL] Fake tax event → free Sparks. Fix: independently verify via Helius RPC getTransaction(signature) — check program ID, instruction discriminator, amount, treasury recipient. Only then credit.
- [HIGH] Rate limiting on ingest. rateLimit({windowMs:60000, max:120}) + per-signature dedup + per-IP limits.
- [HIGH] Double-credit protection. Idempotency key = tx signature. Use economy-service.grant(userId, amount, reason, idemKey) with idemKey = tax:${signature}:${slot}. applyTransaction UNIQUE constraint is ultimate guard.
- [MEDIUM] Amount validation. Tax revenue must be positive integer in smallest unit. Reject fractional/negative. 3% split uses integer math (like splitAmount in reward-engine.js); treasury absorbs remainder.

**4. Cosmetics Unlock (Holder Check) — HIGH:**
- [HIGH] Read-only balance check can be spoofed. Fix: server calls Helius RPC getTokenAccountsByOwner(wallet, mint); check balance ≥ threshold. Never trust client.
- [HIGH] NVDAx region blocking (US persons). Fix: IP geolocation + KYC attestation; store region_verified_at; re-verify on each unlock. Fail closed.
- [MEDIUM] Wallet ownership proof. User must sign message (Solana signMessage) before balance check is meaningful.

**5. Compliance — HIGH:**
- [HIGH] Securities (Howey test). Pool distributing revenue to token holders based on others' efforts likely passes all 4 prongs. Mitigation: (a) Sparks closed-loop non-transferable non-cashable (no withdraw API — preserve), (b) cosmetics purely aesthetic, (c) legal disclaimer. Engage securities counsel.
- [MEDIUM] Gambling. If Sparks earned by gameplay AND have value, rewards could be gambling winnings. Mitigation: Sparks not redeemable for fiat; no cash-out; game outcomes skill-based (≥60s, ≥3 inputs).
- [MEDIUM] MLM. Referral system has referrer splits. Ensure no recruitment-based compensation beyond existing 5-level cap; no buy-in requirement.
- [LOW] Consumer protection. Age gate (13+ parental consent, 18+ for NVDAx cosmetics). ToS with disclaimers. Audit trail of all grants.

**6. Anti-Farming — HIGH:**
- [HIGH] Match validation: ≥60s play time + ≥3 distinct inputs, server-side. Client-reported play time untrusted. Use server-authoritative game state or signed play receipt.
- [HIGH] Daily caps: per-user Spark earning cap (e.g., 500 Sparks/day from gameplay). Per-user match submission cap (e.g., 20 matches/day). Enforce in economy-service via daily-grant counter.
- [MEDIUM] Bot detection: track input entropy (timing variance, keystroke patterns). Flag accounts with >95% identical input timing. Rate-limit match submissions per IP (max 5 distinct users/IP/day).

**7. Rate Limiting & Abuse — MEDIUM:**
- [MEDIUM] Per-user caps: Sparks balance cap (prevent infinite accumulation). Per-user transaction rate limit (max 10 grants/min).
- [MEDIUM] Per-IP limits: Webhook ingest 120 req/min/IP. Gameplay endpoints 30 req/min/IP. Use existing rateLimit middleware.
- [LOW] Anomaly detection: alert on single user earning >3x median, same IP submitting for >5 accounts, grant amounts exceeding 2x expected tax revenue.

**8. Audit Trail — MEDIUM:**
Must log (append-only, tamper-evident): every tax event (tx sig, slot, amount, treasury recipient, verified, timestamp); every Spark grant (userId, amount, reason, idempotencyKey, source tx sig, timestamp); every holder verification (wallet, token, balance, region, verified_at, method); every rate-limit hit (IP, endpoint, timestamp); every reconciliation (expected vs actual, delta, timestamp); admin actions (who, what, when via requireAdminUser from auth-guard).

Pattern reference: ledger model from economy-service.js (append-only spark_transactions) and paybox-guard.js (500-entry rolling calls array). Extend with bridge_audit_log table.

**Summary of Critical Path (ship blockers):** (1) On-chain verification before any Spark credit. (2) Multisig treasury. (3) Server-side holder verification with wallet signature proof. (4) Region blocking for NVDAx (fail closed). (5) Closed-loop Sparks — no withdraw/cash-out API. (6) Legal review for securities/gambling before mainnet.

## DP7. QUILL — SPEC-economy.md (Draft v0.1)

Written to `Shaddai/docs/SPEC-economy.md` (514 words, 8 sections).

**1. Round-up:** Stripe purchases round up to nearest $1 USD. Opt-in at checkout, default off. UI prompt: "Round up $X.XX to $Y.00? (+Z Sparks)". Crypto-in: no round-up. Round-up credit posts after Stripe payment settles. [OWNER DECISION]

**2. Sparks:** 1 Spark = $1 USD, fixed, no float. Ledger in economy-service.js (PostgreSQL in prod). Balance read via GET /api/economy/balance. Fractional: round down to whole Sparks; remainder stays as credit cents in separate float ledger. No cash-out, no transfer, no redemption.

**3. Plots:** Fixed supply 10,000. Cost: 100 Sparks each. Buy via POST /api/plots/claim (idempotent on plotId+userId). Resellable via bazaar at market price. Unsold: 20% reserved for founders (2,000), 80% (8,000) public. Once sold out: secondary market only. [OWNER DECISION]

**4. Fee Pool:** Feeds from (a) 5% bazaar marketplace fee, (b) 20% platform cut on agent job settlements, (c) 3% ASIMOV tax bridge. Settles weekly, Monday 00:00 UTC. Stored in fee_pool table (period, amount, source_breakdown JSONB). Pool amount = share of fees actually collected; never a promised rate. [OWNER DECISION]

**5. Payout:** Formula: per_plot = (pool_amount / num_active_plots) × plot_multiplier. plot_multiplier: 1.0 default; 1.5 for founders plots. Worked examples: Pool $10,000, 500 active plots → $20/plot. 10,000 users, 2,000 active plots, $50,000 pool → $25/plot. 100 users, 50 plots, $500 pool → $10/plot. Empty pool → per_plot = 0; UI shows "Pool empty this period." [OWNER DECISION]

**6. NFT Benefits:** Badge NFT tiers Prospect→Grandmaster. Grants: (a) plot priority (founders first), (b) fee-pool multiplier +0.1 per tier (max +0.5 for Grandmaster), (c) cosmetic unlocks. No cash value. Provenance via IPFS hash. [OWNER DECISION]

**7. SHADDAI Coin:** Conversion: Sparks → coin at 100:1 (100 Sparks = 1 coin). Disclaimer (verbatim in UI): "SHADDAI coin is speculative. No guaranteed value. No cash-out. Not an investment." No in-game utility beyond cosmetic/governance signaling. [OWNER DECISION]

**8. Failure Modes:** (a) Empty pool → plots pay 0, UI "Pool empty this period." (b) Refund → round-up Sparks clawed back; negative balance allowed up to −50, then blocked. (c) Plot supply sells out → secondary market only (bazaar). [OWNER DECISION]

**Owner Decisions Summary:** All bracketed items require explicit owner sign-off before build. Payouts are a share of actually collected fees, computed after the fact; no promised, projected, or advertised rate of return in product copy.

---
*Deep planning compiled by QUILL · SHADDAI Council · 2026-11-03*
*Sources: SHADDAI (orchestrator), NEXUS (architecture), ZEROX (economy), ORACLE (research), TURTLE (venue), PIKADON (security), QUILL (spec).*
'
