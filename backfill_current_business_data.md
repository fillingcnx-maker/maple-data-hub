# Backfill current business data

- Generated: `2026-09-17T04:46:27.836Z`
- Scope: Filling Cafe and Filling Steak
- Period: `2026-09-10` to `2026-09-17`
- Source revision used for the capture: `58f7ee85f118a279203b37accaa33f67a8d4c647`
- Status: **BLOCKED for Cloud reconciliation and BOM movement**

## What was retrieved

GPOS backoffice pages were read for every open date: 10, 11, 12, 13, 14, 16 and 17 September. The live menu report was paginated and captured for each date. Tuesday 15 September is marked closed and was not written as a zero-sales business day.

Merchant evidence was read from the two authorized Gmail sessions:

| Store | Platform | Evidence available | Important limitation |
|---|---|---|---|
| Filling Cafe | Grab | daily statement through 14 Sep; Thaiช่วยไทยพลัส separated | later daily statements not found in this mailbox capture; bank payout is not inferred |
| Filling Cafe | LINE MAN Wongnai | daily report through 16 Sep | report value is present but confirmed payout is missing |
| Filling Cafe | ShopeeFood | daily/bounded attachments through 16 Sep | carry-forward/no-withdrawal states are kept separate |
| Filling Steak | Grab | daily statement through 14 Sep; Thaiช่วยไทยพลัส separated | later daily statements not found in this mailbox capture; bank payout is not inferred |
| Filling Steak | LINE MAN Wongnai | daily report through 16 Sep | report value is present but confirmed payout is missing |
| Filling Steak | ShopeeFood | daily statements through 14 Sep and a 15–16 Sep combined report | combined period is not allocated to a single day |

## GPOS daily totals

| Business date | Gross | Discount | Net | Orders | Payment labels read | Item report |
|---|---:|---:|---:|---:|---|---|
| 2026-09-10 | ฿9,880.00 | ฿789.00 | ฿9,091.00 | 44 | Online STEAK, โอน, ONLINE COFFEE | captured / 6 pages |
| 2026-09-11 | ฿11,761.00 | ฿1,369.00 | ฿10,392.00 | 50 | Online STEAK, ONLINE COFFEE, โอน, Cash | captured / 6 pages |
| 2026-09-12 | ฿15,290.00 | ฿1,012.00 | ฿14,278.00 | 74 | Online STEAK, ONLINE COFFEE, Cash, โอน | captured / 7 pages |
| 2026-09-13 | ฿13,890.00 | ฿1,693.50 | ฿12,196.50 | 71 | Online STEAK, ONLINE COFFEE, โอน, Cash | captured / 9 pages |
| 2026-09-14 | ฿11,435.00 | ฿1,114.00 | ฿10,321.00 | 51 | Online STEAK, ONLINE COFFEE, โอน, Cash | captured / 7 pages |
| 2026-09-16 | ฿12,154.00 | ฿1,002.00 | ฿11,152.00 | 53 | Online STEAK, โอน, Cash, ONLINE COFFEE | captured / 7 pages |
| 2026-09-17 | ฿1,823.00 | ฿195.00 | ฿1,628.00 | 12 | ONLINE COFFEE, โอน, Cash | captured / 2 pages |

The figures above are GPOS source totals. They are not final store revenue or net profit because the live item report contains both businesses while the private Maple menu/store master is not bound.

## Why Cloud/BOM was not written

The backoffice source is readable, but the current private Maple pipeline has no configured GPOS input path for this capture. In addition, the current costing domain has no complete menu catalog/store mapping. Creating a synthetic receipt identifier or assigning mixed items from payment labels would create a false reconciliation and could cut BOM stock incorrectly.

Therefore:

- Cloud reconciliation remains `null` / **BLOCKED**.
- BOM movement remains `null` / **BLOCKED**.
- Cost per menu remains `null` where the costing master is not available.
- Merchant report periods spanning multiple days remain grouped and are not averaged.
- Thaiช่วยไทยพลัส is retained as a separate government-paid bucket, not a Grab bank payout.

## Required system fixes

1. Bind the captured GPOS menu report to Maple with the actual source period and source identifiers.
2. Bind the current menu catalog/store mapping and costing masters.
3. Keep statement net income, government-program income, fees and confirmed payout in separate fields.
4. Only then reconcile Cloud, create BOM movement, and finalize daily/weekly/monthly profit and loss.

The machine-readable source evidence is in `backfill_current_business_data.json`. Missing values are intentionally `null`; no missing payout, menu mapping, or cost was replaced with zero.
