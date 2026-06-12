# โฟลเดอร์ `.claude`

โฟลเดอร์นี้เป็นโฟลเดอร์ตั้งค่าสำหรับ **Claude Code** - เครื่องมือ CLI อย่างเป็นทางการของ Anthropic สำหรับทำงานร่วมกับ Claude

## ไฟล์ในโฟลเดอร์นี้

| ไฟล์ | วัตถุประสงค์ |
|------|-------------|
| `settings.json` | ไฟล์ตั้งค่าหลักของโปรเจกต์ กำหนด plugins ที่เปิดใช้งาน, hooks, permissions, environment variables และการตั้งค่าอื่นๆ |
| `README.md` | ไฟล์คู่มือนี้ |

## Plugins ที่เปิดใช้งาน (จาก `settings.json`)

| Plugin | สถานะ | คำอธิบาย |
|--------|--------|-----------|
| `frontend-design@claude-plugins-official` | ✅ เปิด | ช่วยสร้าง UI/UX components คุณภาพสูง |
| `code-review@claude-plugins-official` | ✅ เปิด | ทำ code review อัตโนมัติ |
| `context7@claude-plugins-official` | ✅ เปิด | ดึงเอกสารประกอบ (documentation) ล่าสุดของไลบรารีต่างๆ |
| `code-simplifier@claude-plugins-official` | ✅ เปิด | ลดความซับซ้อนของโค้ด ทำให้อ่านง่ายขึ้น |
| `claude-md-management@claude-plugins-official` | ✅ เปิด | จัดการไฟล์ CLAUDE.md ให้ทันสมัย |
| `feature-dev@claude-plugins-official` | ✅ เปิด | ช่วยพัฒนาฟีเจอร์ใหม่ด้วย architecture ที่ดี |
| `claude-code-setup@claude-plugins-official` | ✅ เปิด | แนะนำ automation สำหรับ Claude Code |
| `superpowers@claude-plugins-official` | ❌ ปิด | ฟีเจอร์ขั้นสูงเพิ่มเติม (ยังไม่ได้เปิดใช้) |

## โฟลเดอร์ย่อยที่อาจพบได้

| โฟลเดอร์ | วัตถุประสงค์ |
|----------|-------------|
| `agents/` | Custom subagents ที่สร้างขึ้นเอง |
| `commands/` | Custom slash commands |
| `hooks/` | Hook scripts สำหรับ automation |
| `worktrees/` | Git worktrees สำหรับงานที่ต้องแยก environment |
| `projects/` | Project-specific memories และ context |

## การใช้งาน

- ไฟล์ `settings.json` จะถูกโหลดอัตโนมัติเมื่อรัน `claude` ในโปรเจกต์นี้
- การเปลี่ยนแปลง settings ต้อง restart Claude Code เพื่อให้มีผล
- สามารถเพิ่ม hooks, permissions, env vars ได้ตามต้องการ

## หมายเหตุ

> โฟลเดอร์นี้ควร commit เข้า git เพื่อให้ทีมงานใช้ settings เดียวกันได้
> ไฟล์ที่มีข้อมูลละเอียดอ่อน (secrets, API keys) **ห้าม** วางไว้ในนี้โดยตรง - ให้ใช้ environment variables แทน