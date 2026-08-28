# The Quebec Winter Tire Problem

Every fall, sales reps in Quebec started hearing the same thing from garage owners: *"Sorry — we already ordered from someone else."* It kept happening right before winter tire season, the busiest stretch of the year, and always for the same reason — orders weren't showing up in time.

Leadership had complaints, but no numbers. Before committing budget to fix anything, they needed to know: was this actually happening, how much was it costing, and why?

## Confirming the complaint

The first question wasn't "why" — it was "is this even real." Looking at winter tire orders specifically (rather than every order, which would have hidden the effect), one region stood out immediately.

![Winter tire backordered and cancelled orders by province](assets/winter_backorder_by_province.png)

Quebec wasn't just the worst region — it wasn't close. Once turned into a rate rather than a raw count, Quebec's winter tire backorder rate came out to roughly **29%**, compared to **4–8%** everywhere else. Order volume across regions was checked too, in case Quebec just processed more orders overall — it didn't. The gap was specific to fulfillment, not demand.

## Putting a number on it

A backorder rate tells you something is wrong. It doesn't tell leadership what it's costing. Pricing out every unfulfilled tire during the September–November buying window turned the pattern into a dollar figure — and showed it wasn't a one-time blip.

![At-risk revenue by month, Quebec winter tires](assets/lost_value_by_month.png)

The same spike, almost to the month, in both years: roughly **$124,000 in at-risk revenue**, spread across 87 orders — and that's a floor, not a ceiling, since it only counts orders that were placed and partly unfulfilled. It doesn't count the customers who never placed an order at all because they went straight to a competitor.

## Finding out why

A pattern that specific, that consistent, pointed to something structural rather than bad luck. Comparing warehouse inventory across every region, month by month, showed exactly where it was coming from.

![Winter tire inventory on hand by province, monthly](assets/inventory_by_province.png)

Four regions held steady stock year-round. Quebec's warehouse collapsed to a fraction of normal levels for four straight months — August through November — right as demand peaked. By the time stock recovered, the season causing the rush was already over.

## What this means

The fix isn't more warehouse capacity — it's timing. Quebec's stock was being drawn down and replenished on the same schedule as every other region, even though its demand curve looks nothing like theirs.

- **Move the replenishment schedule earlier** — stock should peak in June–July, not November, so it's already high when the September rush starts.
- **Give Quebec its own reorder point for winter tires** instead of one flat threshold across every region.
- **Add a pre-season inventory check** (e.g., August 1) as a standing trigger, with enough lead time to reorder before the rush hits.
- **Track this as an ongoing metric** — backorder rate and at-risk revenue by region and season — so the next version of this problem gets caught before a customer ever notices.

None of this requires new headcount or new capacity. It requires the replenishment calendar to match the season it's actually serving.


