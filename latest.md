# MAPLE EXECUTIVE BRIEF

Generated: 2026-09-19T14:35:09.541Z
Publication Status: PROVISIONAL
Data Quality: 100 — VERIFIED
Overall Freshness: CURRENT (0 day(s) old; as of 2026-09-19)

## Sales
Source: GPOS
Business date: 2026-09-19
Status: INCOMPLETE
Total: ฿15883.00
Orders: 63

## Expenses
Source: Expense Control
Business date: 2026-09-19
Status: INCOMPLETE
Total: null
Freshness: CURRENT

## Inventory
Source: Stock System + GPOS BOM + Expense Control
Business date: 2026-09-19
Status: INCOMPLETE
Events: null
Reconciliation: INCOMPLETE
Issues: 0

## Marketing
Source: Meta Ads
Reporting period: 2026-09-19 to 2026-09-19
Status: INCOMPLETE
Spend: null
Attributed revenue: null

## Costing
Source: Canonical Costing Master
Effective date: 2026-09-17
Status: INCOMPLETE
Menus: 111
Complete: 85
Incomplete: 26

## Alerts
- INFO MARKETING_ATTRIBUTION_MISSING (Meta Ads)
- WARNING SALES_DATA_INCOMPLETE (GPOS)
- INFO CALENDAR_SOURCE_UNKNOWN (Google Calendar)
- WARNING COSTING_INCOMPLETE (Canonical Costing Master)

## Blockers
- none (publication is not blocked)

## Missing Data
- Meta Ads 2026-09-19: attributed_revenue — The current Meta export does not contain attributable revenue
- GPOS 2026-09-19: verified_store_mapping — Some receipt lines could not be mapped to a verified store; totals are retained as provisional and not used as final store profit
- Google Calendar 2026-09-19: events — No Google Calendar adapter is configured
- Canonical Costing Master 2026-09-17: cost_per_serving — 26 menu(s) remain incomplete; financial cost stays null for those menus

## Next Actions
- refresh_source from Meta Ads (2026-09-19)
- connect_source from Google Calendar (2026-09-19)
- resolve_costing_missing_data from Canonical Costing Master (2026-09-17)
