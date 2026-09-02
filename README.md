# Payment Dashboard (Tableau Extension)

Tableau Dashboard Extension ที่แสดงสรุปมูลค่า payment รวม, %growth เทียบเดือนก่อน, trend รายวัน, payment แยกตามสาขา/MCH2/sales channel และตาราง raw detail

ดึงข้อมูลจาก BigQuery view: `boonthavorn-data-analytic.tableau.ds_vdo_payment_article_fact`

> **สถานะปัจจุบัน:** `Payment.html` ยังเป็น preview ที่ใช้ sample data (fabricated ให้มีหน้าตา/สัดส่วนใกล้เคียงข้อมูลจริง) ยังไม่ได้ต่อ BigQuery ผ่าน Tableau Extensions API จริง

## ไฟล์ในโปรเจกต์

- `Payment.html` — ตัวหน้า dashboard ทั้งหมด (HTML/CSS/JS แบบ standalone ไม่มี dependency ภายนอกนอกจาก SheetJS สำหรับปุ่มดาวน์โหลด Excel)
- `manifest.trex` — Tableau Dashboard Extension manifest

## Deploy

**Production:** host ผ่าน GitHub Pages ที่ `https://chonnikan-saw03.github.io/payment/Payment.html`

**Local dev:** รัน static server จากโฟลเดอร์นี้ เช่น

```
python -m http.server 8000
```

แล้วเปิด `http://localhost:8000/Payment.html`

## ใช้งานใน Tableau Desktop

1. เปิด workbook → แท็บ Dashboard
2. ลาก object **Extension** ลงบน dashboard
3. เลือก **Access Local Extensions** → เลือกไฟล์ `manifest.trex`
4. ยืนยัน security warning

`manifest.trex` ชี้ไปที่ URL ของ GitHub Pages ด้านบนอยู่แล้ว ใช้ได้ทันทีโดยไม่ต้องรัน local server
