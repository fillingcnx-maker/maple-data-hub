# Costing Missing Data Audit

- Repository: https://github.com/fillingcnx-maker/maple-executive-os
- Branch: main
- Source revision: aae97a3afb7a5dd7b78eae2c7e374bcc0e8fc014
- Generated: 2026-09-17T08:30:55.398Z
- Status: **AUDIT_COMPLETE_WITH_MISSING_DATA**

> `null`/missing หมายถึงไม่มีหลักฐานที่คำนวณได้ ไม่ใช่ศูนย์ และไม่มีการเดาสูตร ปริมาณ หน่วย หรือราคา

## สรุป

- เมนูทั้งหมด: **111**
- Costing ครบ: **83**
- Costing ยังขาด: **28**
- แถวต้นทุนวัตถุดิบที่ source ยังขาด: **9**
- Owner actions ที่ต้องแก้จริง: **12**

## สูตรและกติกา

`cost per serving = sum(recipe quantity converted to canonical unit × canonical unit cost) + packaging cost`

- ใช้ Recipe/BOM เวอร์ชันล่าสุดที่มี provenance
- ใช้ unit cost จาก canonical `unit_costs` เท่านั้น
- ไม่มี direct/default/promo fallback
- หากตัวเลือกหลายแบบไม่มีค่าเลือกที่ยืนยันได้ จะเป็น MAPPING_ERROR และไม่แทนด้วยศูนย์

## สถานะแยกร้าน

### Filling Cafe

- เมนูทั้งหมด: **51**
- คำนวณต้นทุนครบ: **41**
- ยังขาด: **10**
- รายการที่คำนวณไม่ได้: CAFE-COFFEE-CARAMEL Caramel Macchiato, CAFE-COFFEE-ORANGE Orange Coffee, CAFE-SMOOTHIE-APPLE Apple Smoothie, CAFE-CAKE-010 เค้กหมี, CAFE-BAKERY-002 Muffin chocolate, CAFE-SODA-STRAWBERRY Strawberry Soda, CAFE-SODA-BLUEBERRY Blueberry Soda, CAFE-SODA-LYCHEE Lychee Soda, CAFE-SODA-MANGO Mango Soda, CAFE-SODA-APPLE Apple Soda

### Filling Steak

- เมนูทั้งหมด: **60**
- คำนวณต้นทุนครบ: **42**
- ยังขาด: **18**
- รายการที่คำนวณไม่ได้: STK-001 สเต็กหมู, STK-002 สเต็กไก่, STK-003 สเต็กปลาทอด, STK-004 สเต็กไส้กรอกรวม, STK-008 Pork Chop, STK-005 สเต็ก Ribeye / เนื้อสันแหลม, STK-006 สเต็ก Striploin / เนื้อสันนอก, STK-007 สเต็ก Picanha, CMB-003 สเต็กหมู + ไก่, SET-M Set M, SET-L Set L, SET-XL Set XL, CMB-001 สเต็กหมู + หมู, CMB-002 สเต็กไก่ + ไก่, CMB-004 สเต็กหมู + ปลาทอด, CMB-005 สเต็กหมู + ไส้กรอกรวม, CMB-006 สเต็กไก่ + ปลาทอด, CMB-007 สเต็กไก่ + ไส้กรอกรวม

## เมนูที่คำนวณได้ครบ

| ร้าน | Menu SKU | เมนู | Variant | Cost/serving (บาท) | Recipe version |
|---|---|---|---|---:|---|
| Filling Cafe | CAFE-COFFEE-AMER-MID | Americano / AMERICANO-กลาง | delivery | 19.5925 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-AMER-DARK | Americano / AMERICANO-เข้ม | delivery | 22.1275 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-LATTE | Latte | delivery | 26.7950 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-CAPPUCCINO | Cappuccino | delivery | 25.2050 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-ESPRESSO | Espresso เย็น / ESPRESSO | delivery | 24.1800 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-MOCHA | Mocha / Mocha-กลาง | delivery | 29.4012 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-COCONUT | Coconut Black | delivery | 49.5750 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-HONEY-LEMON | Black Honey Lemon | delivery | 19.5925 | 2026-09-17 |
| Filling Cafe | CAFE-COFFEE-LEMON | Black Lemon | delivery | 19.5925 | 2026-09-17 |
| Filling Cafe | CAFE-MILK-FRESH | Fresh Milk | delivery | 17.3717 | 2026-09-17 |
| Filling Cafe | CAFE-MILK-PINK | Pink Milk | delivery | 18.4160 | 2026-09-17 |
| Filling Cafe | CAFE-MILK-STRAWBERRY-PINK | Strawberry Pink Milk | delivery | 20.9960 | 2026-09-17 |
| Filling Cafe | CAFE-MILK-CARAMEL | Caramel Milk | delivery | 20.2033 | 2026-09-17 |
| Filling Cafe | CAFE-MILK-HONEY | Honey Milk | delivery | 19.1531 | 2026-09-17 |
| Filling Cafe | CAFE-COCOA | Cocoa / โกโก้ | delivery | 21.0798 | 2026-09-17 |
| Filling Cafe | CAFE-CHOCOLATE | Chocolate Premium | delivery | 53.0325 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-THAI | Thai Tea / THAI TEA | delivery | 32.0673 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-GREEN | Green Tea / Green TEA | delivery | 32.0673 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-THAI-FRAPPE | Thai Tea Frappe | delivery | 25.6184 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-GREEN-FRAPPE | Green Tea Frappe | delivery | 25.6184 | 2026-09-17 |
| Filling Cafe | CAFE-SMOOTHIE-STRAWBERRY | Strawberry Smoothie | delivery | 34.0036 | 2026-09-17 |
| Filling Cafe | CAFE-SMOOTHIE-BLUEBERRY | Blueberry Smoothie | delivery | 35.6536 | 2026-09-17 |
| Filling Cafe | CAFE-MATCHA-LATTE | Matcha Latte | delivery | 58.8100 | 2026-09-17 |
| Filling Cafe | CAFE-MATCHA-COCONUT | Matcha Coconut / Coconut Matcha | delivery | 62.7700 | 2026-09-17 |
| Filling Cafe | CAFE-MATCHA-PURE | Pure Matcha | delivery | 33.1200 | 2026-09-17 |
| Filling Cafe | CAFE-SODA-PEACH | Peach Soda | delivery | 18.9419 | 2026-09-17 |
| Filling Cafe | CAFE-SODA-LEMON | Lemon Soda | delivery | 18.9419 | 2026-09-17 |
| Filling Cafe | CAFE-SODA-HONEY-LEMON | Honey Lemon Soda | delivery | 18.9419 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-LEMON | Lemon Tea | delivery | 15.0601 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-HONEY-LEMON | Honey Lemon Tea | delivery | 15.0601 | 2026-09-17 |
| Filling Cafe | CAFE-TEA-PEACH | Peach Tea | delivery | 15.0601 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-001 | Orange Cake | delivery | 80.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-002 | Coconut Cake | delivery | 80.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-003 | เค้กกล้วยหอม | delivery | 45.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-004 | เค้กกล้วยหอมคาราเมล | delivery | 80.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-005 | ชีสเค้กหน้าไหม้ | delivery | 70.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-006 | เค้กชาไทย | delivery | 50.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-007 | เค้กชาเขียว | delivery | 60.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-008 | Black Forest Cake | delivery | 80.0200 | 2026-09-17 |
| Filling Cafe | CAFE-CAKE-009 | Red Velvet Cake | delivery | 80.0200 | 2026-09-17 |
| Filling Cafe | CAFE-BAKERY-001 | แปงชูวิสครัวซองค์ | delivery | 70.0200 | 2026-09-17 |
| Filling Steak | PST-001 | สปาเก็ตตี้คาโบนาร่า | dine-in | 35.9701 | 2026-09-17 |
| Filling Steak | PST-002 | สปาเก็ตตี้ครีมกุ้ง | dine-in | 63.9051 | 2026-09-17 |
| Filling Steak | PST-003 | สปาเก็ตตี้ผัดขี้เมา | dine-in | 28.9116 | 2026-09-17 |
| Filling Steak | PST-006 | สปาเก็ตตี้ซอสมะเขือเทศหมูสับ | dine-in | 46.0262 | 2026-09-17 |
| Filling Steak | SND-001 | Club Sandwich / คลับแซนด์วิช | dine-in | 35.6588 | 2026-09-17 |
| Filling Steak | SNK-001 | ทอดรวม | dine-in | 54.6710 | 2026-09-17 |
| Filling Steak | SNK-002 | เอ็นไก่ทอด | dine-in | 50.6496 | 2026-09-17 |
| Filling Steak | SNK-003 | หมูแดดเดียว | dine-in | 25.2453 | 2026-09-17 |
| Filling Steak | SNK-005 | เฟรนช์ฟรายส์ขายแยก | dine-in | 14.1091 | 2026-09-17 |
| Filling Steak | SLD-001 | สลัดน้ำมันงาญี่ปุ่น | dine-in | 38.0000 | 2026-09-17 |
| Filling Steak | SLD-002 | สลัดปูอัดไข่กุ้ง | dine-in | 60.6350 | 2026-09-17 |
| Filling Steak | SLD-003 | Caesar Salad | dine-in | 51.4622 | 2026-09-17 |
| Filling Steak | SNK-006 | มันบดขายแยก | dine-in | 5.5181 | 2026-09-17 |
| Filling Steak | MOD-SAUCE-01 | เพิ่มซอสปลาทอด | dine-in | 6.9761 | 2026-09-17 |
| Filling Steak | PST-007 | สปาเก็ตตี้พริกแห้งเบคอน | dine-in | 12.6159 | 2026-09-17 |
| Filling Steak | DRK-002 | โค้ก Original / มีน้ำตาล | dine-in | 13.0800 | 2026-09-17 |
| Filling Steak | DRK-003 | โค้ก Zero / ไม่มีน้ำตาล | dine-in | 13.9200 | 2026-09-17 |
| Filling Steak | PST-004 | สปาเก็ตตี้เพสโต้กุ้ง | dine-in | 63.6273 | 2026-09-17 |
| Filling Steak | PST-005 | สปาเก็ตตี้เพสโต้เนื้อ | dine-in | 57.6273 | 2026-09-17 |
| Filling Steak | BGR-001 | Everyday Burger เนื้อ | dine-in | 88.5619 | 2026-09-17 |
| Filling Steak | BGR-002 | Everyday Burger หมู | dine-in | 73.5619 | 2026-09-17 |
| Filling Steak | BGR-003 | Everyday Burger ไก่ย่าง | dine-in | 70.5619 | 2026-09-17 |
| Filling Steak | BGR-004 | Everyday Burger ไก่ทอด | dine-in | 66.4619 | 2026-09-17 |
| Filling Steak | BGR-005 | Big Bike Burger เนื้อ | dine-in | 155.5819 | 2026-09-17 |
| Filling Steak | BGR-006 | Big Bike Burger หมู | dine-in | 125.5819 | 2026-09-17 |
| Filling Steak | BGR-007 | Big Bike Burger ไก่ย่าง | dine-in | 119.5819 | 2026-09-17 |
| Filling Steak | BGR-008 | Big Bike Burger ไก่ทอด | dine-in | 111.3819 | 2026-09-17 |
| Filling Steak | BGR-009 | Melt More Burger เนื้อ | dine-in | 117.0519 | 2026-09-17 |
| Filling Steak | BGR-010 | Melt More Burger หมู | dine-in | 102.0519 | 2026-09-17 |
| Filling Steak | BGR-011 | Melt More Burger ไก่ย่าง | dine-in | 99.0519 | 2026-09-17 |
| Filling Steak | BGR-012 | Melt More Burger ไก่ทอด | dine-in | 94.9519 | 2026-09-17 |
| Filling Steak | MOD-ADDON-BURGER-BEEF-CHEESE-GRILLED-CHICKEN | แอดออนเบอร์เกอร์: แพตตี้เนื้อ + ชีส + ไก่ย่าง | dine-in | 70.0000 | 2026-09-17 |
| Filling Steak | SNK-004 | หมูคำหวาน | dine-in | 30.6946 | 2026-09-17 |
| Filling Steak | DRK-001 | น้ำเปล่าสิงห์ | dine-in | 3.9200 | 2026-09-17 |
| Filling Steak | DRK-004 | โซดาสิงห์ | dine-in | 9.0000 | 2026-09-17 |
| Filling Steak | DRK-005 | น้ำแร่ Charles House | dine-in | 5.0000 | 2026-09-17 |
| Filling Steak | DRK-006 | น้ำแข็ง 1 ถัง | dine-in | 2.0000 | 2026-09-17 |
| Filling Steak | DRK-007 | เบียร์สิงห์ขวดใหญ่ | dine-in | 57.5000 | 2026-09-17 |
| Filling Steak | DRK-008 | เบียร์สิงห์ โปร 3 ขวด | dine-in | 172.5000 | 2026-09-17 |
| Filling Steak | SRV-001 | ค่าเปิดเหล้า | dine-in | 0.0000 | 2026-09-17 |
| Filling Steak | SRV-002 | ค่าเปิดไวน์ | dine-in | 0.0000 | 2026-09-17 |
| Filling Steak | PREP-PEP | ซอสพริกไทยดำ | dine-in | 3.2295 | 2026-09-17 |

## เมนูที่คำนวณไม่ได้ / รายการที่ติด

| ร้าน | Menu SKU | เมนู | Ingredient/SKU | Missing field | สาเหตุจริง | Source ที่ควรมีข้อมูล | Status | Owner ต้องแก้ |
|---|---|---|---|---|---|---|---|---|
| Filling Cafe | CAFE-COFFEE-CARAMEL | Caramel Macchiato | — | sweetness_selection | No verified sweetness option/default is available for this menu | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Cafe | CAFE-COFFEE-ORANGE | Orange Coffee | — | sweetness_selection | No verified sweetness option/default is available for this menu | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Cafe | CAFE-SMOOTHIE-APPLE | Apple Smoothie | FC-ING-019-A | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SMOOTHIE-APPLE | Apple Smoothie | FC-ING-016 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Steak | STK-001 | สเต็กหมู | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-002 | สเต็กไก่ | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-003 | สเต็กปลาทอด | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-004 | สเต็กไส้กรอกรวม | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-008 | Pork Chop | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-005 | สเต็ก Ribeye / เนื้อสันแหลม | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-006 | สเต็ก Striploin / เนื้อสันนอก | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | STK-007 | สเต็ก Picanha | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-003 | สเต็กหมู + ไก่ | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | SET-M | Set M | — | coke_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | SET-L | Set L | — | coke_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | SET-XL | Set XL | — | coke_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-001 | สเต็กหมู + หมู | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-002 | สเต็กไก่ + ไก่ | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-004 | สเต็กหมู + ปลาทอด | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-005 | สเต็กหมู + ไส้กรอกรวม | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-006 | สเต็กไก่ + ปลาทอด | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Steak | CMB-007 | สเต็กไก่ + ไส้กรอกรวม | — | side_selection | Source defines multiple options but no verified selection/default was available | Recipe/BOM Master / verified menu option or default | MAPPING_ERROR | ใช่ |
| Filling Cafe | CAFE-CAKE-010 | เค้กหมี | FC-CAKE-010 | unit_cost | Owner requested the menu/SKU but no purchase unit cost was supplied | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-BAKERY-002 | Muffin chocolate | FC-BAKERY-002 | unit_cost | Owner requested the menu/SKU but no purchase unit cost was supplied | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-BAKERY-002 | Muffin chocolate | — | packaging_sku | Component SKU is missing | Recipe/BOM Master and canonical costing pipeline | MAPPING_ERROR | ไม่ใช่ |
| Filling Cafe | CAFE-SODA-STRAWBERRY | Strawberry Soda | FC-ING-037 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-BLUEBERRY | Blueberry Soda | FC-ING-037 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-LYCHEE | Lychee Soda | FC-ING-019-L | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-LYCHEE | Lychee Soda | FC-ING-068 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-LYCHEE | Lychee Soda | FC-ING-037 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-MANGO | Mango Soda | FC-ING-019-M | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-MANGO | Mango Soda | FC-ING-018 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-MANGO | Mango Soda | FC-ING-037 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-APPLE | Apple Soda | FC-ING-019-A | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-APPLE | Apple Soda | FC-ING-016 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |
| Filling Cafe | CAFE-SODA-APPLE | Apple Soda | FC-ING-037 | unit_cost | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Ingredient Master / canonical unit_costs | SOURCE_MISSING | ใช่ |

## Audit แหล่งข้อมูล

| Dataset | Status | Canonical source | Reason |
|---|---|---|---|
| Ingredient Master | CANONICAL | Expense Control seed-data.js + unit-cost-conversions.js | — |
| Recipe/BOM Master — Filling Cafe | CANONICAL | Expense Control cafe-recipes.js | — |
| Recipe/BOM Master — Filling Steak | CANONICAL | Expense Control steak-catalog.js + steak-bom-updates.js | — |
| Packaging SKU | CANONICAL | Expense Control inventoryItems + recipe packaging components | — |
| Unit Conversion | CANONICAL | Expense Control unit-cost-conversions.js + stock-cost-utils.js | — |
| SKU Mapping | CANONICAL_WITH_REVIEW_GUARD | Expense Control gpos-menu-mapping.js | Heuristic mapping is not accepted for financial truth |
| Stock Deduction | CANONICAL_WITH_SAFETY_GUARD | Expense Control gpos-stock-deduction.js | Movement is allowed only for complete costing |
| Obsidian recipe cards | STALE | Obsidian business notes | Older revision than the 2026-09-17 Expense Control source |
| Maple costing master before import | MISSING | Private repo | No central costing domain existed before this import |
| Owner-requested menu updates | CANONICAL_OVERLAY | Owner instruction 2026-09-17 | Explicit menu/SKU/formula update; missing prices remain null |

## Pipeline ที่แก้แล้ว

- **PIPELINE_NO_COSTING_DOMAIN** (FIXED_IN_THIS_CHANGE): Maple previously had sales/inventory aggregates but no canonical Ingredient, Recipe/BOM, Packaging, Unit Cost, or Costing domain. — Read the canonical costing master and use costing.mjs for menu costing and stock deduction.
- **PIPELINE_AUDIT_FALSE_MISSING** (FIXED_IN_THIS_CHANGE): The previous audit only searched Maple paths and reported all costing sources as missing even though configured Expense Control source records existed. — Audit the imported canonical master menu-by-menu and retain source provenance.
- **PIPELINE_BATCH_FIELD_MISMATCH** (FIXED_IN_THIS_CHANGE): Batch source uses yieldQty while normalized master uses yield_quantity; nested batch costing previously stopped at a false mapping error. — Normalize both source field names and calculate nested batch cost only when yield unit matches.
- **PIPELINE_HEURISTIC_SKU_FALLBACK** (GUARDED): Legacy GPOS menu mapping has a heuristic fallback; it is not allowed to create financial truth or stock movement without verified mapping. — Keep heuristic matches as review-only and require canonical SKU mapping for posting.
- **LEGACY_ESTIMATED_COGS_OUTSIDE_MAPLE** (NOT_USED_BY_MAPLE): The audited legacy Expense Control UI contains operational benchmark COGS fallback paths; this target-only change does not mutate that source repository. — Maple financial reports must use only canonical costing status and null when incomplete.

## Owner ต้องแก้จริงเท่านั้น

| ID | Missing field | Ingredient/SKU | เหตุผล | เมนูที่ได้รับผลกระทบ |
|---|---|---|---|---|
| OWNER_1 | sweetness_selection | — | No verified sweetness option/default is available for this menu | Filling Cafe: CAFE-COFFEE-CARAMEL<br>Filling Cafe: CAFE-COFFEE-ORANGE |
| OWNER_2 | unit_cost | FC-ING-019-A | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SMOOTHIE-APPLE<br>Filling Cafe: CAFE-SODA-APPLE |
| OWNER_3 | unit_cost | FC-ING-016 | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SMOOTHIE-APPLE<br>Filling Cafe: CAFE-SODA-APPLE |
| OWNER_4 | side_selection | — | Source defines multiple options but no verified selection/default was available | Filling Steak: STK-001<br>Filling Steak: STK-002<br>Filling Steak: STK-003<br>Filling Steak: STK-004<br>Filling Steak: STK-008<br>Filling Steak: STK-005<br>Filling Steak: STK-006<br>Filling Steak: STK-007<br>Filling Steak: CMB-003<br>Filling Steak: CMB-001<br>Filling Steak: CMB-002<br>Filling Steak: CMB-004<br>Filling Steak: CMB-005<br>Filling Steak: CMB-006<br>Filling Steak: CMB-007 |
| OWNER_5 | coke_selection | — | Source defines multiple options but no verified selection/default was available | Filling Steak: SET-M<br>Filling Steak: SET-L<br>Filling Steak: SET-XL |
| OWNER_6 | unit_cost | FC-CAKE-010 | Owner requested the menu/SKU but no purchase unit cost was supplied | Filling Cafe: CAFE-CAKE-010 |
| OWNER_7 | unit_cost | FC-BAKERY-002 | Owner requested the menu/SKU but no purchase unit cost was supplied | Filling Cafe: CAFE-BAKERY-002 |
| OWNER_8 | unit_cost | FC-ING-037 | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SODA-STRAWBERRY<br>Filling Cafe: CAFE-SODA-BLUEBERRY<br>Filling Cafe: CAFE-SODA-LYCHEE<br>Filling Cafe: CAFE-SODA-MANGO<br>Filling Cafe: CAFE-SODA-APPLE |
| OWNER_9 | unit_cost | FC-ING-019-L | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SODA-LYCHEE |
| OWNER_10 | unit_cost | FC-ING-068 | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SODA-LYCHEE |
| OWNER_11 | unit_cost | FC-ING-019-M | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SODA-MANGO |
| OWNER_12 | unit_cost | FC-ING-018 | Referenced by a current BOM but no usable canonical unit cost is available for this recipe unit | Filling Cafe: CAFE-SODA-MANGO |

รายการนี้ไม่รวมปัญหาที่ pipeline แก้เองได้ และไม่รวมข้อมูลที่ถูกพบแล้วใน canonical master

## Validation

- duplicate menu SKU: **0**
- missing recipe identity: **0**
- missing recipe source: **0**
- raw/source overwritten: **ไม่ใช่**
