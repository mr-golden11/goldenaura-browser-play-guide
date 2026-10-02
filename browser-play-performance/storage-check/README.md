# Storage Check — Verify Browser Cache in DevTools

This note shows how anyone can reproduce a lightweight storage check for GoldenAura browser play in Chrome DevTools. No install and no backend code are needed. The expected pattern is small, on-demand loading: about 1.6s to interactive start and roughly 6–9MB per 100 spins, because thumbnails and game shells load first while heavy scenes wait until use.

Follow these steps to reproduce the check:

1. Open https://goldenaura.cloud/games/ and pick any title, for example Sweet Bonanza at https://goldenaura.cloud/games/SweetBonanza/.
2. Press F12 to open DevTools, then open the Network tab with caching enabled normally and Preserve log turned off for a clean run.
3. Reload the game page and watch the Status, Size, and Time columns until the spin button becomes interactive, about 1.6s on a warmed connection.
4. Spin slowly for 10 rounds, note the Transferred total at the bottom, then multiply by 10 to estimate per-100-spin load in the expected 6–9MB range.
5. Open Application, then Storage, Cache Storage, and Local Storage to confirm only normal browser cache entries exist with no extra payloads.
6. Use Clear site data to reset, then reload and repeat with a second title from the library to confirm lazy-load behavior where repeated symbols come from cache.
7. If transferred size keeps growing without reuse, close extra tabs, clear cache once, and retest at an unhurried pace.

This is a generic browser pattern description only, with no server or integration details included.

Full library: https://goldenaura.cloud/games/. Hub: https://goldenaura.cloud/. Educational overview. Check in-game help for official rules. 18+. Play responsibly.
