# Wheel of Luck — Guide

Bonus Hub reward: free spins on a prize wheel. Unlocks by rank, prizes credited instantly. This is an educational guide with no backend here.

Top prize advertised in Bonus Hub: up to $500,000 in BTC. Actual segments pay cash to balance, boosts, free spins, and other rewards.

## How to enter / spin

1. Sign in to GoldenAura and open Bonus Hub / Rewards (`Your Bonus Hub`).
2. Select `Wheel of Luck` (menu item alongside Cashback, Rakeback, Weekly Bonus, Monthly Bonus).
3. If spins are available for your rank/activity, press Spin. Each available spin is free.
4. Prize credits instantly to balance, or boost activates automatically.

Availability is rank-based:

- Wheel unlocks once you reach the required rank.
- Available spins depend on current rank and activity.
- Spins reset on a recurring basis. No spins = play more / rank up, then check back.

If locked, the panel shows eligibility state only — no spin button.

## Segments / prizes

From `config/rewards.php` — `wheel` block:

- Cash prizes credited to your balance
- Rakeback and Cashback boosts
- Free spins and other rewards

Boost rules (same file, `rakeback.boost`):

- Boost = +50% over your base rakeback rate, activated automatically after you receive it.
- Duration: 50% boost for 1 hour — from Wheel spins, and separately 50% boost for 1 hour for claiming Regular & Calendar bonuses.
- Stacking: level/duration cannot be increased by multiple claims, with one exception — a boost won in the Wheel of Luck increases the duration of your active boost.

Other sources players confuse with this wheel:

- In-game slot wheels such as `ZodiacWheelEGT` / `SuperWheelPG` are separate casino games under `games describtion readme files/`, not this Bonus Hub wheel.

## Draws / reset model

This is not a numbered lottery draw. There are no draw IDs, no 6-number tickets, no 8 PM UTC cut-off.

- Continuous Bonus Hub reward, not a scheduled draw.
- For scheduled numbered draws (Daily / Weekly Mega / VIP), see `lottery/` and https://goldenaura.cloud/page/lottery
- Check Bonus Hub for current spin count — that is the source of truth for your account.

## Example

1. Player reaches eligible rank, opens Bonus Hub → Wheel of Luck shows 1 spin available.
2. Player spins → lands cash segment → amount goes 50/50 or 100% per Bonus Distribution rule, or straight to balance for VIP (see Terms).
3. Next spin lands `50% Rakeback Boost 1h` → boost auto-activates, rakeback accrues at 1.5× base rate for the next hour.
4. Player spins again while boost is active and wins another Wheel boost → duration extends (Wheel-only stacking exception).
5. No spins left → panel shows empty state until next reset.

Amounts, segments, and odds are shown in the live Bonus Hub panel. This README invents no percentages or segment weights.

## Terms (summary, official panel prevails)

- Eligibility: rank-gated. Spins are free when available; no purchase for the spin itself.
- Distribution: `Bonus Distribution` rule from rewards config applies to claimable bonus amounts:
  - Rank 0–29: 50% to balance, 50% to calendar for 3 days.
  - VIP users: 100% to balance.
  - Minimum $0.01/day to calendar; smaller remainder goes to balance in full.
- Rakeback eligibility context (same file): Casino bets — Slots, GoldenAura Originals; Live casino bets from Gold (VIP) rank in Evolution / Pragmatic Play / Ezugi games count for rakeback rate that the boost multiplies.
- Accrual periods / rate structure shown in Bonus Hub prevail over this summary.
- 18+. Play responsibly. Check official rules in the live panel before spinning.

## Visual sources

From `Blog-Website/content/casino-img/`:

- `WheelofLuck.png` — wheel hero art
- `WheelofLuck_bg.png` — wheel background
- `promiton_page/` + `bounce_page/` variants for Bonus Hub placement

No images copied here. Folder + README only.

## Links

- Lottery (numbered draws): https://goldenaura.cloud/page/lottery
- Promotions: https://goldenaura.cloud/page/promotions
- VIP: https://goldenaura.cloud/page/vip
- Games: https://goldenaura.cloud/games/
- GoldenAura: https://goldenaura.cloud

*Educational hub. Folders + READMEs only, no backend here. Check Bonus Hub / in-game help for official rules. 18+. Play responsibly.*
