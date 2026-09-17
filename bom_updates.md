# BOM Policy Update — 17 September 2026

- Source: Filling Cafe Expense Control BOM master
- Effective date: 2026-09-17
- Period: 2026-09-17 ถึง 2026-09-17
- Platform: internal BOM/Costing
- Status: **VERIFIED**
- Automated validation: `npm test` — 220 ผ่าน, 0 ไม่ผ่าน

ไฟล์นี้เป็น snapshot ของการปรับสูตร BOM ล่าสุดสำหรับให้เลขาอ่าน ไม่ใช่รายรับหรือ payout และไม่เขียนทับ movement เดิม

## Filling Cafe

### ค่าเริ่มต้นการคำนวณ

- หมวดกาแฟ: ใช้ระดับ **ไม่หวาน** เป็นค่าเริ่มต้น
- เมนูอื่นที่มีระดับความหวาน: ใช้ **ปกติ** เป็นค่าเริ่มต้น
- ถ้ารายการจริงระบุระดับความหวาน ให้ใช้ค่าที่ระบุแทนค่าเริ่มต้น

### Pure Matcha

- `CAFE-MATCHA-PURE` — ผง Matcha 3 g
- น้ำ `FC-ING-001` = **120 ml** ตีกับ Matcha
- น้ำแข็ง `FC-ING-002` = 180 g
- ลบการเติมน้ำเย็น 120 ml แยกซ้ำออกแล้ว

### ชาสกัดสด

| เมนู | ไซรัปประจำเมนู | น้ำเชื่อมตามระดับความหวาน |
|---|---|---|
| Lemon Tea | `FC-ING-013` 40 ml | `FC-ING-008`: 25%=10 ml, 50%=15 ml, ปกติ=20 ml |
| Honey Lemon Tea | `FC-ING-012` 40 ml | `FC-ING-008`: 25%=10 ml, 50%=15 ml, ปกติ=20 ml |
| Peach Tea | `FC-ING-014` 40 ml | `FC-ING-008`: 25%=10 ml, 50%=15 ml, ปกติ=20 ml |

## ร้านสเต็ก

### ค่าเริ่มต้นซอส

เมนูที่มีตัวเลือกซอสให้เริ่มคำนวณจาก `PREP-GRV` ซอสเกรวี่ 37 g ก่อน หากรายการจริงระบุซอสพริกไทยดำ ให้เปลี่ยนเป็น `PREP-PEP` ตามรายการนั้น

เมนูที่ใช้กฎนี้: `STK-001`, `STK-002`, `STK-004`, `STK-005`, `STK-006`, `STK-007`, `STK-008`, `CMB-001` ถึง `CMB-007`

### Set และ Coke

| Set | จำนวน Coke |
|---|---:|
| Set M (`SET-M`) | 2 กระป๋อง |
| Set L (`SET-L`) | 3 กระป๋อง |
| Set XL (`SET-XL`) | 4 กระป๋อง |

ชนิด Coke ต้องอ่านจากรายละเอียดจริงว่า Original หรือ Zero หากไม่ระบุให้ขึ้น “ต้องตรวจ” ไม่เลือกแทนเอง

### สเต็กปลาทอด

- `STK-003` — ซอสสลัด `PREP-SLD` **50 g** อย่างเดียว
- ไม่มีตัวเลือกซอสในเมนูนี้

### เพิ่มซอสปลาทอด

- `MOD-SAUCE-01` — ซอสสลัด `PREP-SLD` **50 g**
- Delivery ใช้ถุงซิปล็อก 8×12 ซม. SKU `RAW-PKG-038` จำนวน 1 ใบ
- ราคาแพ็ก 18 บาท/100 ใบ
- ต้นทุนต่อใบ **0.18 บาท**

## สิ่งที่เลขาควรใช้เป็นหลัก

1. ใช้สูตรและค่าเริ่มต้นจากไฟล์นี้เมื่อทำ costing รอบใหม่
2. ไม่นำรายงานนี้ไปรวมเป็นรายรับหรือ payout
3. ไม่ตั้ง Coke Original/Zero เองถ้ารายการขายไม่ระบุ
4. เก็บข้อมูลการใช้จริงตาม Menu SKU และร้านแยกกัน

## Source trace

- `expense-tracker/cafe-recipes.js`
- `expense-tracker/steak-catalog.js`
- `expense-tracker/steak-bom-updates.js`
- `expense-tracker/bom-costing.js`
- `expense-tracker/gpos-stock-deduction.js`
