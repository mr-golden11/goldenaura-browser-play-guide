# Weekly Race 20K — Guide

Wager race with a $20,000 prize pool and a live leaderboard. Race by wagering; top places split the pool. This is an educational guide with no backend here.

Do not confuse with the sidebar `10K Wager Race` banner — that is a separate promo. This folder covers the $20,000 Weekly Race.

## How the leaderboard works

From `partials/live-bets-table.blade.php` — `weekly_race` tab, and `lang/en/ui.php`:

- Tab: `Weekly Race` under All Bets / High Rollers.
- Banner stats: Total Prize ($20,000 default), Total Winners, Time Remaining (`DDd HHh MMm`).
- Table columns: Place, User, Points, Percent, Rewards.
- Points accrue from qualifying wagers during the race week. Higher wager volume = more points = higher place.
- Percent = your share of the pool. Rewards column = your payout for that place.
- Places 1–3 get trophy highlight (`lb-place-1/2/3`).
- Timer counts down to reset; standings freeze at the end of the period.

Check the live Weekly Race tab for current pool, places paid, and minimum qualifying play. That panel is the source of truth.

## Example

1. Player wagers through the week on slots and climbs to place 5.
2. Leaderboard shows 12,500 points, 4% share.
3. At a $20,000 pool, 4% = $800 illustrative reward.
4. Timer hits zero → standings lock → prize credits per official race rules.
5. Player outside paid places gets no race payout but keeps any Bonus Hub rakeback/cashback accrued separately.

Points-to-payout mapping and paid places are shown live. This example invents no payout table.

## Terms (summary, official panel prevails)

- Prize pool advertised: $20,000. Paid places and splits shown in the live leaderboard prevail.
- Entry is by qualifying wagering during the race period; no separate ticket.
- Reset is weekly. Time Remaining in the race banner governs the cut-off.
- Separate `10K Wager Race` sidebar promo has its own banner and timer.
- 18+. Play responsibly. Check official rules at https://goldenaura.cloud/page/promotions before racing.

## Visual sources

From `Blog-Website/content/casino-img/`:

- `20kweeklyrace.jpg` — weekly race hero art

No images copied here. Folder + README only.

## Links

- Promotions: https://goldenaura.cloud/page/promotions
- VIP: https://goldenaura.cloud/page/vip
- Games: https://goldenaura.cloud/games/
- GoldenAura: https://goldenaura.cloud

*Educational hub. Folders + READMEs only, no backend here. Check Bonus Hub / in-game help for official rules. 18+. Play responsibly.*
