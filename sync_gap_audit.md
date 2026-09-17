# Maple Sync Gap Audit

- Repository: https://github.com/fillingcnx-maker/maple-executive-os
- Generated: 2026-09-17T08:46:03.105Z
- Status: **BLOCKED_NO_TRANSACTION_SOURCE**

## Root cause

- **ROOT_NO_INPUT_PATH** (CONFIRMED): Current runtime has no GPOS_INPUT_PATH, STOCK_INPUT_PATH, or STOCK_AUTO_INPUT_PATH configured. Evidence: apps/worker/src/config.mjs, .env.example
- **ROOT_NO_RUNTIME_RECORDS** (CONFIRMED): Current staging database contains no raw records, sales, inventory events, or checkpoints; recent runs are publish-brief only and failed at the data gate. Evidence: staging runtime database, apps/worker/src/cli.mjs
- **ROOT_HEALTH_EXISTENCE_ONLY** (CONFIRMED): The historical GPOS health check recorded HEALTHY/last_sync while the latest business date remained 2026-09-09 because it checked source availability, not source business-date freshness. Evidence: reports/maple/source_health.json, packages/core/src/adapters.mjs
- **ROOT_SCHEDULER_NOT_IN_REPO** (CONFIRMED): config/schedules.json defines recurring jobs, but this private repo contains no executable scheduler or job-executor entry that proves sync jobs ran after 2026-09-09. Evidence: config/schedules.json, apps/worker/src/cli.mjs
- **ROOT_REPORT_NOT_REGENERATED** (CONFIRMED): The tracked report bundle is still business_date 2026-09-09; publish copied that bundle and therefore public data stayed stale. This is not a CDN-only issue. Evidence: reports/maple/latest.json, reports/maple/sales.json, reports/maple/manifest.json

## Source verification: 2026-09-10 ถึง 2026-09-17

| Date | Store status | Source capture | Transaction source | Sales orders found | Inventory events | Sync required | Reason |
|---|---|---|---|---:|---:|---|---|
| 2026-09-10 | OPEN | ใช่ | ไม่พบ | 44 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |
| 2026-09-11 | OPEN | ใช่ | ไม่พบ | 50 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |
| 2026-09-12 | OPEN | ใช่ | ไม่พบ | 74 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |
| 2026-09-13 | OPEN | ใช่ | ไม่พบ | 71 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |
| 2026-09-14 | OPEN | ใช่ | ไม่พบ | 51 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |
| 2026-09-15 | CLOSED | ไม่พบ | ไม่พบ | — | — | ไม่ใช่ | Tuesday is configured as a closed weekday; no sales=0 row is created. |
| 2026-09-16 | OPEN | ใช่ | ไม่พบ | 53 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |
| 2026-09-17 | OPEN | ใช่ | ไม่พบ | 12 | — | ใช่ | Source evidence exists after 2026-09-09, but no transaction-level input path is configured and no order/receipt records are present in the repo for safe ingestion. |

## Checkpoint before fix

- Last successful sync in current runtime DB: **—**
- Checkpoints: **0**
- Raw records: **0**
- Sales records: **0**
- Inventory events: **0**
- Historical published GPOS health: HEALTHY; business date 2026-09-09; last sync 2026-09-14T15:26:16.086Z

## Backfill result

**NOT_POSTED** — พบ aggregate evidence หลังวันที่ 9 แต่ไม่มี transaction-level source ใน repo/runtime จึงไม่สร้างยอดขายหรือ movement ปลอม

## Future sync

- Backfill: `npm run backfill -- gpos`
- Incremental: `npm run sync -- gpos`
- ลำดับ: health freshness check → fetch only new records → normalize → validate → reconcile → save checkpoint → generate reports → publish
- Idempotent: **ใช่**
- วันปิดร้านสร้างยอด 0: **ไม่ใช่**

## Reports before fix

- Latest: 2026-09-09
- Sales: 2026-09-09
- Inventory: 2026-09-09
- Generated: 2026-09-16T04:12:11.176Z

Latest business date is intentionally unchanged until a configured transaction-level source is supplied and passes validation.
