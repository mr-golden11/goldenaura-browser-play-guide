# Lazy-Load Pattern — Browser Play Performance (GoldenAura)

Generic frontend pattern note for fast game lobbies at GoldenAura Casino. It describes — without proprietary code or backend details — how image/iframe lazy-loading with `IntersectionObserver` plus early-connection hints (`preconnect` / `dns-prefetch`) keeps the playable library fast in instant browser play.

Browse the library this pattern supports: https://goldenaura.cloud/games/
Hub: https://goldenaura.cloud

## What it is

Lazy-loading defers offscreen work until it is needed. In a lobby with hundreds of game tiles, thumbnails and demo iframes below the fold are not fetched on first paint — they load as the player scrolls near them. Above-the-fold tiles load immediately; everything else waits.

This is a pure frontend, no-backend-calls pattern. No game API, cashier, RNG, or session logic is involved.

## Generic pattern (describe, don't paste)

1. **Native lazy as baseline.** Mark lobby images with `loading="lazy"` and `decoding="async"`, with explicit `width`/`height` to avoid layout shift. This alone covers most modern browsers.
2. **IntersectionObserver for control.** For finer control (tile grids, tabbed lobbies, iframe previews), observe each placeholder with a generic `IntersectionObserver` with a small `rootMargin` (e.g. preload slightly before entry). On intersect: swap `data-src` → `src` (or attach iframe), then `unobserve()` the entry so it fires once. Disconnect the observer when the list unmounts.
3. **Preconnect to media hosts only.** Add `<link rel="preconnect">` (with `crossorigin` where needed) for the 1–2 image/game-asset hosts actually used on first scroll, plus `dns-prefetch` fallback for older browsers. Do not preconnect to every provider host — that defeats the purpose.
4. **Guardrails.** Keep a `noscript` / no-JS fallback (plain links to game pages), never lazy-load above-the-fold hero tiles, and cancel/offload observers on route change.

No proprietary implementation is reproduced here — the above is the public pattern only.

## Official docs (read these, not site source)

- IntersectionObserver — https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API
- Lazy loading images / `loading` attribute — https://developer.mozilla.org/en-US/docs/Web/Performance/Lazy_loading
- `preconnect` / `dns-prefetch` resource hints — https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/rel/preconnect
- Lighthouse / PageSpeed guidance on offscreen images — https://developers.google.com/speed/docs/insights/

## GoldenAura links

- Full game library: https://goldenaura.cloud/games/
- Example titles: https://goldenaura.cloud/games/GatesofOlympus/ — https://goldenaura.cloud/games/SweetBonanza/ — https://goldenaura.cloud/games/StarBurstNET/
- Hub: https://goldenaura.cloud — Promotions: https://goldenaura.cloud/page/promotions — VIP: https://goldenaura.cloud/page/vip — Lottery: https://goldenaura.cloud/page/lottery

## License

MIT — this note describes a generic public web-performance pattern. Reuse the idea freely in your own code; consult the MDN/docs links above for canonical API details.

*Educational frontend note only. No backend, server, RNG, or integration details included. 18+ only. Play responsibly.*
