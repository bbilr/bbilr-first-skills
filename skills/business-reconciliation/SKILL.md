---
name: business-reconciliation
description: Reconcile marketplace orders, settlements, bank records, and aggregator reports, or calculate source-backed per-order contribution. Use for business cash-flow checks, duplicate-source control, pricing, and Ads break-even analysis; not for securities trading or statutory tax conclusions.
---

# Business Reconciliation

Keep sales, settlement, cash, and control totals distinct so the same money is not counted twice.

## Source And Period

- Identify period, currency, timezone, row grain, and provenance for each source. Keep original data intact.
- Use order records for order activity, platform settlement records for payouts and fees, and bank statements for actual cash movements. An aggregator such as BigSeller is a reconciliation control when it repeats platform activity, not additional revenue.
- Inspect identifiers, coverage, and duplicate exports before combining files. Deduplicate supported matches; preserve uncertain matches for review.
- Do not classify unreviewed bank rows as business receipts or expenses. Separate transfers, timing differences, refunds, canceled orders, and personal or unidentified transactions.

## Reconciliation

1. Establish source totals and link rows using available order, settlement, payout, or transaction identifiers. Date and amount alone may be ambiguous.
2. Explain the bridge between order activity, settlement adjustments, and bank receipts. Keep unmatched items visible rather than forcing a balance.
3. State `verified`, `partial`, and `needs review` for the relevant scope. Keep computed totals separate from estimates and unresolved items.

## Contribution And Ads

- Calculate from the money retained by the seller. If starting from net settlement, do not subtract already-deducted fees or discounts again.
- Account for COGS, seller-funded discounts, shipping, platform/payment fees, returns, and attributed acquisition cost where available. Free gifts may have zero revenue and nonzero cost.
- Distinguish per-order contribution from accounting profit and cash flow; identify overhead and timing exclusions.
- Report attributed ROAS only when attribution data supports it. Blended revenue divided by Ads spend is a blended ratio, not proof of attributed performance.
- Use current source-backed costs and fee terms. If absent, give formulas or labeled scenarios instead of invented prices or budgets.

## Deliverable

Lead with the result and its completeness. Include a compact reconciliation or price/contribution table, source references, formulas, and unresolved items that affect the decision. If files are requested, create them and verify formulas and control totals before reporting completion.
