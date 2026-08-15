# 💌 เว็บเซอร์ไพรส์วันเกิด

เว็บ static ไฟล์เดียว (`index.html`) มี 3 ฉาก: จดหมายมาส่ง → เปิดจดหมายฟังเสียงอวยพร + อัปโหลดรูปของขวัญ → Happy Birthday 🎉

## 1. ใส่ไฟล์ของคุณ (วางในโฟลเดอร์เดียวกับ index.html)

| ไฟล์ | คืออะไร |
|---|---|
| `blessing.mp3` | เสียงอวยพรที่คุณอัดเอง |
| `happy-birthday.mp3` | เพลง Happy Birthday (เล่นวนหน้าสุดท้าย) |
| `my-photo.jpg` | รูปคุณ (โชว์ในกรอบโพลารอยด์หน้าสุดท้าย) |

ถ้าไฟล์ไหนหาย เว็บไม่พัง — เสียงจะมีปุ่ม "ข้ามไปก่อน" และรูปจะโชว์ 🥳 แทน

## 2. สร้าง Discord Webhook (รับรูปของขวัญ)

1. เปิด Discord → สร้าง server ส่วนตัว (หรือใช้ที่มีอยู่)
2. คลิกขวา channel → **Edit Channel → Integrations → Webhooks → New Webhook**
3. กด **Copy Webhook URL**
4. เปิด `index.html` หา `CONFIG` (บนสุดของ `<script>`) แล้ววาง URL แทน `PASTE_YOUR_DISCORD_WEBHOOK_URL_HERE`

พอแฟนกดยืนยัน รูปจะเด้งเข้า channel นั้นทันที (ถ้าส่งไม่สำเร็จ เว็บจะไปหน้า 3 ต่อเลย ไม่ทำให้เซอร์ไพรส์พัง)

> ⚠️ Webhook URL จะมองเห็นได้ในโค้ด — ใช้ channel ที่ไม่สำคัญ และลบ webhook ทิ้งหลังวันเกิดได้เลย

## 3. เปลี่ยนข้อความ/ชื่อ

- ชื่อแฟน: แก้ `girlfriendName` ใน `CONFIG`
- ข้อความต่างๆ: แก้ตรงๆ ในส่วน HTML ได้เลย (ค้นหาข้อความในไฟล์)

## 4. ขึ้น GitHub Pages

1. สร้าง repo ใหม่บน GitHub (ตั้งชื่อกลางๆ กันแฟนเดา เช่น `little-mail`)
2. อัปโหลด `index.html` + ไฟล์ mp3/รูป ทั้งหมดขึ้น repo
3. ไปที่ **Settings → Pages → Source: Deploy from a branch → main → / (root)** → Save
4. รอ 1-2 นาที ได้ลิงก์ `https://<username>.github.io/<repo>/` ส่งให้แฟนได้เลย

## ทดสอบก่อนส่ง

ดับเบิลคลิกเปิด `index.html` ในเครื่องได้เลย (ทุกอย่างทำงาน รวมถึงส่ง Discord)
