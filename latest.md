# MAPLE EXECUTIVE BRIEF

Generated: 2026-09-15T15:01:24.638Z
Publication Status: PROVISIONAL
Data Quality: 75 — INCOMPLETE
Overall Freshness: STALE (5 day(s) old; as of 2026-09-14)

## Sales
Source: GPOS
Business date: 2026-09-09
Status: VERIFIED
Total: ฿11518.02
Orders: 62

## Expenses
Source: Expense Control
Business date: 2026-08-30
Status: VERIFIED
Total: ฿400.00
Freshness: STALE

## Inventory
Source: Stock System + GPOS BOM + Expense Control
Business date: 2026-09-09
Status: INCOMPLETE
Events: 6
Reconciliation: INCOMPLETE
Issues: 4

## Marketing
Source: Meta Ads
Reporting period: 2026-08-15 to 2026-09-13
Status: INCOMPLETE
Spend: ฿2628.34
Attributed revenue: null

## Alerts
- WARNING INVENTORY_MISSING_CLOSING (Stock System)
- WARNING INVENTORY_MISSING_CLOSING (Stock System)
- WARNING INVENTORY_MISSING_CLOSING (Stock System)
- WARNING INVENTORY_MISSING_CLOSING (Stock System)
- WARNING SOURCE_STALE (Expenses)
- WARNING SOURCE_STALE (Inventory)
- INFO MARKETING_ATTRIBUTION_MISSING (Meta Ads)
- INFO CALENDAR_SOURCE_UNKNOWN (Google Calendar)

## Blockers
- none (publication is not blocked)

## Missing Data
- Stock System 2026-09-09: closing_actual — No actual closing count was found in the stock source
- Stock System 2026-09-09: closing_actual — No actual closing count was found in the stock source
- Stock System 2026-09-09: closing_actual — No actual closing count was found in the stock source
- Stock System 2026-09-09: closing_actual — No actual closing count was found in the stock source
- Meta Ads 2026-09-13: attributed_revenue — The current Meta export does not contain attributable revenue
- Google Calendar 2026-09-15: events — No Google Calendar adapter is configured

## Next Actions
- read_actual_closing_stock from Stock System (2026-09-09)
- refresh_source from Expense Control (2026-08-30)
- refresh_source from Meta Ads (2026-09-13)
- connect_source from Google Calendar (2026-09-15)
