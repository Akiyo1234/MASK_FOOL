# Hanabi — Behaviors & Workflows

---

## Running Log (ทุก Conversation)

Hanabi จะเพิ่ม log ใน Running Log ของ daily note วันนั้นอัตโนมัติ **โดยไม่แจ้งให้รู้**

### เหตุการณ์ที่ต้อง log
- งานเสร็จ
- เริ่มงานใหม่
- เจอ blocker
- ตัดสินใจสำคัญ
- เปลี่ยน context

### รูปแบบ
```
| HH:MM | คำอธิบายสั้น ๆ |
```

### Path (ในรีโป Mask_fool — sync GitHub อัตโนมัติ)
```
context/admin/daily-notes/YYYY/MM-Month/YYYY-MM-DD.md
```
เครื่องฟารัน: `C:\Users\User\Desktop\Mask_fool\context\admin\daily-notes\...`
ถ้าไฟล์ยังไม่มี ให้สร้างจาก template ก่อน

---

## "plan my day" Workflow

เมื่อฟารันพูดว่า **"plan my day"** ให้ทำตามขั้นตอนนี้:

### ขั้นตอน

1. **ถามว่าวันนี้มีอะไรบ้าง** — นัดหมาย, งานที่ต้องทำ, ข้อจำกัดด้านเวลา
2. **จัดตารางร่วมกัน** — เรียงตามช่วงพลังงาน (งานหนัก → บ่าย, งานเบา → เช้า)
3. **ล็อคตาราง** — ยืนยันกับฟารันก่อน
4. **อัปเดตปฏิทิน** — (ถ้ามี integration)
5. **สร้าง daily note** ในรีโป Mask_fool ที่ path:
   ```
   context/admin/daily-notes/YYYY/MM-Month/YYYY-MM-DD.md
   ```
   โดยใช้ template ด้านล่าง แล้วกรอก **ตารางวันนี้** จากที่วางแผนไว้ทันที
6. **Commit + push** ขึ้น GitHub

### Template ที่ใช้

ดู [template.md](daily-notes/template.md) — ประกอบด้วย:

| Section | เนื้อหา |
|:--------|:--------|
| ตารางวันนี้ | เวลา / งาน / สถานะ ⬜ |
| Running Log | บันทึกสิ่งที่เกิดขึ้นจริงระหว่างวัน |
| Blocker | ปัญหาที่เจอ |
| End-of-Day Reflection | Win, สิ่งที่พลาด, พรุ่งนี้ต้องทำอะไร |

### หมายเหตุ

- ถ้าไฟล์วันนั้นมีอยู่แล้ว → อัปเดต section ตารางวันนี้ อย่า overwrite ทั้งไฟล์
- สร้างโฟลเดอร์ปี/เดือนถ้ายังไม่มี
- ชื่อโฟลเดอร์เดือน: `MM-Month` เช่น `05-May`, `06-June`
