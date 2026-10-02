# Lottery — Guide

Numbered lottery: pick 6 numbers from 1–49, buy a ticket for a specific draw, match to win. Daily and Weekly draws plus a VIP-only draw. This is an educational guide with no backend here.

Live page: https://goldenaura.cloud/page/lottery

## How to enter / buy a ticket

From `config/lottery.php` + `pages/lottery.blade.php`:

1. Open https://goldenaura.cloud/page/lottery and pick an open draw (All / Daily / Weekly Mega / VIP tabs).
2. Choose 6 unique numbers from 1 to 49, or use Quick Pick for random selection.
3. Press Buy Ticket / Quick Pick for that draw ID. Each ticket is linked to one specific draw.
4. Pay from casino balance. Confirm in `Select Your Numbers` → `Confirm Purchase` modal.
5. Wait for the scheduled draw. Countdown is shown live per card + hero (`Next Draw`).
6. Collect: prizes credited instantly to balance — no claim form.

Gates:

- Logged out → `Sign in to buy tickets.`
- Insufficient balance → `Insufficient balance — deposit to continue.` → `/cashier?tab=deposit`
- VIP draw locked → `VIP status or $1,000+ balance required.` Buy / Quick Pick buttons disabled until eligible.

## Tickets / segments

- Selection: 6 unique numbers, 1–49.
- Ticket card shows: ticket price, `Draws in` countdown (`schedule_time`), `Sold` (current / max if capped), `Your tickets` count.
- Quick Pick = random 6. Clear / re-pick before confirm. Cost and balance shown in modal (`Ticket Cost`, `Your Balance`).
- One purchase can create multiple tickets for the same draw; each ticket stores its own 6 numbers.

Prize tiers from `config/lottery.php` (`prize_tiers`):

| Match | Prize | Pool / note |
| --- | --- | --- |
| 6 + Bonus | Jackpot | 60% of pool |
| 6 | Tier 1 | Fixed prize |
| 5 + Bonus | Tier 2 | Fixed prize |
| 5 | Tier 3 | Fixed prize |
| 4 + Bonus | Tier 4 | Fixed prize |
| 4 | Tier 5 | Free ticket |
| 3 + Bonus | Tier 6 | Consolation |

Fixed-prize figures, jackpot seed, and ticket price are per-draw live values on `/page/lottery`. This README invents no amounts.

Trust badges on hero: Provably Fair, Instant Payouts, Secure Draws.

## Draws

From `config/lottery.php` (`draw_types`) + blade schedule fields:

- Daily Draw — Every day at 8:00 PM UTC. Badge: Popular.
- Weekly Mega — Every Sunday at 8:00 PM UTC. Badge: Big Jackpot.
- VIP Draw — Exclusive high-stakes draw. Badge: VIP Only. Requires VIP status or $1,000+ balance.

Page sections: Open Draws, How It Works (4 steps: Pick → Buy → Wait → Collect), Prize Tiers, Recent Winners, Draw Results, My Tickets.

Empty states: `No open draws right now. Check back soon.` / `No winners yet — be the first!` / `No completed draws yet.` / `You have no tickets yet.`

Results show winning numbers + matched count per ticket. Winnings auto-credit.

## Example

1. Daily Draw #142 shows Jackpot $12,400, ticket $2, `Draws in 04:12:33`, Sold 318/1000, Your tickets 0.
2. Player picks 4-11-19-27-33-45, Confirms. Balance −$2. Card updates to Your tickets 1.
3. Player Quick Picks 2 more tickets for same draw. Your tickets 3.
4. At 8:00 PM UTC draw runs, winning numbers 4-11-19-27-33-02 + Bonus 45.
   - Ticket 1 matches 5 + Bonus → Tier 2 fixed prize, credited instantly.
   - Quick Pick tickets match 3 / 4 → Tier 6 consolation / Tier 5 free ticket per table above.
5. Player checks Draw Results / My Tickets: numbers, matched count, jackpot label per ticket.

Numbers and prizes above are illustrative. Check the live draw card and results tab for official values.

## Terms (summary, official page prevails)

- 6 unique numbers 1–49 per ticket, bound to one draw ID. No number changes after purchase.
- Scheduled draws run automatically; countdown / `schedule_time` on the card is authoritative.
- VIP draw gated: VIP status or $1,000+ balance. Locked cards cannot be bought.
- Payouts credited to casino balance instantly; no manual claim in current flow.
- Ticket price, max tickets per draw, jackpot pool split, and fixed-tier amounts are per-draw live values.
- 18+. Play responsibly. Check official rules on https://goldenaura.cloud/page/lottery before buying.

## Visual sources

From `Blog-Website/content/casino-img/lottery/` (mirrored to `minimal/img/lottery/`):

- `hero-banner.png` — lottery hero background
- `ticket.png` / `ticket.webp` — ticket icon on hero + draw cards
- `gold.png` / `gold.webp` — jackpot stat icon
- `spin.png` / `spin.webp` — next-draw countdown icon
- `claim.png` / `claim.webp` — tickets-sold stat icon
- `banners/lottery.png` — promotions banner variant

No images copied here. Folder + README only.

## Links

- Lottery: https://goldenaura.cloud/page/lottery
- Promotions: https://goldenaura.cloud/page/promotions
- VIP: https://goldenaura.cloud/page/vip
- Cashier (deposit for tickets): https://goldenaura.cloud/cashier
- Games: https://goldenaura.cloud/games/
- GoldenAura: https://goldenaura.cloud

*Educational hub. Folders + READMEs only, no backend here. Check /page/lottery and in-game help for official rules and prize figures. 18+. Play responsibly.*
