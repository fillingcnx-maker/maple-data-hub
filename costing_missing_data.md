# Costing Missing Data Audit

- Repository: https://github.com/fillingcnx-maker/maple-executive-os
- Branch: main
- Source revision: e5a0eb6d6cda957b19848501c4c913df15ee18f4
- Scope: private repo only; Filling Cafe และ Filling Steak
- Status: **BLOCKED_BY_MISSING_COSTING_SOURCES**
- Generated: 2026-09-17T01:41:16.933Z

> ค่า `null` หรือ `—` หมายถึงไม่มีหลักฐานใน repo นี้ ไม่ใช่ศูนย์ และไม่มีการเดาข้อมูลแทน

## สรุป

- เมนูทั้งหมด: **—**
- Costing ครบ: **—**
- Costing ยังขาด: **—**
- Owner actions ที่ต้องแก้จริง: **4 กลุ่มข้อมูลต้นทาง**

ไม่สามารถนับเมนูหรือยืนยันต้นทุนต่อเมนูได้ เพราะ private repo นี้ไม่มี menu catalog และไม่มี costing masters ที่จำเป็น

## สูตรที่ใช้ตรวจ

`cost per serving = sum(recipe quantity converted to ingredient base unit × ingredient unit cost) + sum(packaging quantity × packaging unit cost)`

ต้องมีครบทั้ง Menu SKU, Ingredient SKU, quantity, unit, conversion, unit cost และ packaging ต่อ serving จึงจะคำนวณได้

## Audit แหล่งข้อมูล

| Dataset | Status | Evidence in repo | Missing fields ที่ต้องใช้ |
|---|---|---|---|
| Ingredient Master | MISSING | — | ingredient_sku<br>ingredient_name<br>base_unit<br>unit_cost<br>currency<br>source |
| Recipe/BOM Master | MISSING | — | menu_sku<br>menu_name<br>business_unit<br>ingredient_sku<br>quantity<br>unit |
| Packaging SKU | MISSING | — | packaging_sku<br>packaging_name<br>unit_cost<br>unit<br>quantity_per_serving |
| Costing | MISSING | — | menu_sku<br>cost_per_serving<br>cost_components<br>calculated_at<br>source |
| Stock Mapping | MISSING | — | menu_sku<br>ingredient_sku<br>source_unit<br>target_unit<br>conversion_factor |
| Menu Catalog | MISSING | — | menu_sku<br>menu_name<br>business_unit<br>active |

## สถานะแยกร้าน

### Filling Cafe

- สถานะ: NOT_AUDITABLE_WITH_REPO_DATA_ONLY
- จำนวนเมนู: —
- เมนูที่คำนวณได้ครบ: —
- เมนูที่คำนวณไม่ได้: —
- เหตุผล: ไม่มีเมนูของร้านนี้ใน private repo จึงไม่สร้างชื่อหรือ SKU ขึ้นเอง

### Filling Steak

- สถานะ: NOT_AUDITABLE_WITH_REPO_DATA_ONLY
- จำนวนเมนู: —
- เมนูที่คำนวณได้ครบ: —
- เมนูที่คำนวณไม่ได้: —
- เหตุผล: ไม่มีเมนูของร้านนี้ใน private repo จึงไม่สร้างชื่อหรือ SKU ขึ้นเอง

## เมนูที่คำนวณได้ครบ

ยังไม่มีรายการที่ยืนยันได้จาก repo นี้ จึงเป็นรายการว่าง ไม่ได้แปลว่าทุกเมนูมีต้นทุนเป็นศูนย์

## เมนูที่คำนวณไม่ได้

ไม่สามารถสร้างรายชื่อเมนูได้ เพราะไม่พบ Menu Catalog/Menu SKU ของทั้งสองร้าน การสร้างชื่อเมนูจากยอดรวมจะเป็นการ fabricate

## Missing ทั้งหมด

| Dataset | Store | Menu SKU | Missing field | Reason | Source ที่ควรมีข้อมูล | Status |
|---|---|---|---|---|---|---|
| Ingredient Master | — | — | ingredient_sku | ไม่พบ source record/file/table ที่ยืนยัน ingredient_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Ingredient Master | OWNER_REQUIRED |
| Ingredient Master | — | — | ingredient_name | ไม่พบ source record/file/table ที่ยืนยัน ingredient_name ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Ingredient Master | OWNER_REQUIRED |
| Ingredient Master | — | — | base_unit | ไม่พบ source record/file/table ที่ยืนยัน base_unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Ingredient Master | OWNER_REQUIRED |
| Ingredient Master | — | — | unit_cost | ไม่พบ source record/file/table ที่ยืนยัน unit_cost ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Ingredient Master | OWNER_REQUIRED |
| Ingredient Master | — | — | currency | ไม่พบ source record/file/table ที่ยืนยัน currency ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Ingredient Master | OWNER_REQUIRED |
| Ingredient Master | — | — | source | ไม่พบ source record/file/table ที่ยืนยัน source ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Ingredient Master | OWNER_REQUIRED |
| Recipe/BOM Master | — | — | menu_sku | ไม่พบ source record/file/table ที่ยืนยัน menu_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Recipe/BOM Master | OWNER_REQUIRED |
| Recipe/BOM Master | — | — | menu_name | ไม่พบ source record/file/table ที่ยืนยัน menu_name ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Recipe/BOM Master | OWNER_REQUIRED |
| Recipe/BOM Master | — | — | business_unit | ไม่พบ source record/file/table ที่ยืนยัน business_unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Recipe/BOM Master | OWNER_REQUIRED |
| Recipe/BOM Master | — | — | ingredient_sku | ไม่พบ source record/file/table ที่ยืนยัน ingredient_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Recipe/BOM Master | OWNER_REQUIRED |
| Recipe/BOM Master | — | — | quantity | ไม่พบ source record/file/table ที่ยืนยัน quantity ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Recipe/BOM Master | OWNER_REQUIRED |
| Recipe/BOM Master | — | — | unit | ไม่พบ source record/file/table ที่ยืนยัน unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Recipe/BOM Master | OWNER_REQUIRED |
| Packaging SKU | — | — | packaging_sku | ไม่พบ source record/file/table ที่ยืนยัน packaging_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Packaging SKU | OWNER_REQUIRED |
| Packaging SKU | — | — | packaging_name | ไม่พบ source record/file/table ที่ยืนยัน packaging_name ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Packaging SKU | OWNER_REQUIRED |
| Packaging SKU | — | — | unit_cost | ไม่พบ source record/file/table ที่ยืนยัน unit_cost ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Packaging SKU | OWNER_REQUIRED |
| Packaging SKU | — | — | unit | ไม่พบ source record/file/table ที่ยืนยัน unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Packaging SKU | OWNER_REQUIRED |
| Packaging SKU | — | — | quantity_per_serving | ไม่พบ source record/file/table ที่ยืนยัน quantity_per_serving ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Packaging SKU | OWNER_REQUIRED |
| Costing | — | — | menu_sku | ไม่พบ source record/file/table ที่ยืนยัน menu_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Costing | OWNER_REQUIRED |
| Costing | — | — | cost_per_serving | ไม่พบ source record/file/table ที่ยืนยัน cost_per_serving ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Costing | OWNER_REQUIRED |
| Costing | — | — | cost_components | ไม่พบ source record/file/table ที่ยืนยัน cost_components ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Costing | OWNER_REQUIRED |
| Costing | — | — | calculated_at | ไม่พบ source record/file/table ที่ยืนยัน calculated_at ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Costing | OWNER_REQUIRED |
| Costing | — | — | source | ไม่พบ source record/file/table ที่ยืนยัน source ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Costing | OWNER_REQUIRED |
| Stock Mapping | — | — | menu_sku | ไม่พบ source record/file/table ที่ยืนยัน menu_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Stock Mapping | OWNER_REQUIRED |
| Stock Mapping | — | — | ingredient_sku | ไม่พบ source record/file/table ที่ยืนยัน ingredient_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Stock Mapping | OWNER_REQUIRED |
| Stock Mapping | — | — | source_unit | ไม่พบ source record/file/table ที่ยืนยัน source_unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Stock Mapping | OWNER_REQUIRED |
| Stock Mapping | — | — | target_unit | ไม่พบ source record/file/table ที่ยืนยัน target_unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Stock Mapping | OWNER_REQUIRED |
| Stock Mapping | — | — | conversion_factor | ไม่พบ source record/file/table ที่ยืนยัน conversion_factor ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Stock Mapping | OWNER_REQUIRED |
| Menu Catalog | — | — | menu_sku | ไม่พบ source record/file/table ที่ยืนยัน menu_sku ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Menu Catalog | OWNER_REQUIRED |
| Menu Catalog | — | — | menu_name | ไม่พบ source record/file/table ที่ยืนยัน menu_name ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Menu Catalog | OWNER_REQUIRED |
| Menu Catalog | — | — | business_unit | ไม่พบ source record/file/table ที่ยืนยัน business_unit ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Menu Catalog | OWNER_REQUIRED |
| Menu Catalog | — | — | active | ไม่พบ source record/file/table ที่ยืนยัน active ใน repo นี้; จึงไม่สามารถคำนวณต้นทุนต่อ serving ได้ | private repo source for Menu Catalog | OWNER_REQUIRED |

## Pipeline / mapping findings

| Finding | Severity | Status | Reason | Evidence | Remediation |
|---|---|---|---|---|---|
| PIPELINE_NO_COSTING_DOMAIN | HIGH | PIPELINE_GAP | ไม่มี canonical kind/table/schema สำหรับ Ingredient Master, Recipe/BOM, Packaging หรือ Costing | packages/core/src/pipeline.mjs<br>packages/core/src/canonical.mjs<br>db/sqlite/schema.sql | เพิ่ม source adapter, canonical records, validation และ storage สำหรับ costing ก่อนนำตัวเลขมาใช้ |
| PIPELINE_RECIPE_AS_INVENTORY | HIGH | PIPELINE_GAP | Obsidian ที่อยู่ในโฟลเดอร์ recipes ถูก route เป็น inventory และ normalize เป็น stock event; สูตรจึงไม่กลายเป็น BOM/cost component | packages/core/src/pipeline.mjs<br>packages/core/src/canonical.mjs<br>packages/core/src/adapters.mjs | แยก recipe/BOM normalizer และตรวจ quantity/unit/ingredient SKU แทนการตีความเป็น inventory |
| PIPELINE_REPORTS_ARE_AGGREGATES | HIGH | SOURCE_GRAIN_GAP | sales.json มีเพียงยอดรวมตามร้าน/ช่องทาง และ inventory.json มีเพียง movement item code; ไม่มี menu SKU กับส่วนประกอบสูตร | reports/maple/sales.json<br>reports/maple/inventory.json | ดึงและเก็บ menu-level source ก่อนทำ costing; ไม่แตกยอดรวมเป็นเมนูโดยการเดา |
| PIPELINE_NO_COSTING_PUBLIC_ARTIFACT | MEDIUM | FIXED_IN_THIS_CHANGE | publisher ไม่ได้ allowlist รายงาน audit costing | scripts/publish-maple-data-hub.mjs | เพิ่ม costing_missing_data.json/md ใน public allowlist หลังผ่าน security validation |

## สิ่งที่แก้จาก pipeline

- เพิ่ม audit script ที่แยก source missing, pipeline gap และ Owner action โดยรักษา missing เป็น `null/missing`
- เพิ่มรายงานนี้เข้า publisher allowlist เพื่อให้เผยแพร่ได้หลังผ่าน security validation
- ยังไม่เติม costing record ใด ๆ และยังไม่สร้าง movement เพราะไม่มีสูตร/ต้นทุนต้นทางให้ตรวจสอบ

## Owner ต้องแก้จริงเท่านั้น

| OWNER_INGREDIENT_MASTER | จัดให้มี Ingredient Master ใน source ที่ repo นี้อ่านได้ | ingredient_sku<br>ingredient_name<br>base_unit<br>unit_cost<br>currency<br>source |
| OWNER_RECIPE_BOM_MASTER | จัดให้มี Recipe/BOM Master พร้อมรายการเมนูของทั้งสองร้าน | menu_sku<br>menu_name<br>business_unit<br>ingredient_sku<br>quantity<br>unit |
| OWNER_PACKAGING_SKU | จัดให้มี Packaging SKU และจำนวนใช้ต่อ serving | packaging_sku<br>packaging_name<br>unit_cost<br>unit<br>quantity_per_serving |
| OWNER_STOCK_MAPPING | ยืนยัน Stock Mapping และ unit conversion เฉพาะรายการที่ไม่มีใน source | menu_sku<br>ingredient_sku<br>source_unit<br>target_unit<br>conversion_factor |

รายการนี้ไม่รวมงานที่ระบบควรแก้เอง เช่น การเพิ่ม canonical costing domain, recipe normalizer, unit conversion validation และการดึง menu-level source

## ข้อจำกัด

- repo นี้ไม่มี Ingredient Master, Recipe/BOM Master, Packaging SKU หรือ menu-level costing records
- รายงาน sales/inventory ที่มีอยู่เป็น aggregate/movement evidence ไม่ใช่ costing source
- จึงยังระบุจำนวนเมนูทั้งหมดและจำนวนเมนูที่ costing ครบ/ขาดเป็น null ได้เท่านั้น

## Traceable source facts

- `reports/maple/sales.json`: source=GPOS, business_date=2026-09-09, มีเพียง business-unit/channel aggregate
- `reports/maple/inventory.json`: source=Stock System + GPOS BOM + Expense Control, business_date=2026-09-09, item codes=FC-CAKE-001, FC-CAKE-005, FC-CAKE-003, FC-CAKE-008, ไม่มี unit cost และ recipe quantities
