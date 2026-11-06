# track4-week1 — Workshop 04: AI Vibe Coding

Workshop ฝึกพัฒนาซอฟต์แวร์ครบวงจรร่วมกับ Claude Code ตั้งแต่ User Story → Requirement → Design → Code → Test โดยใช้ Skill ของแต่ละบทบาท (BA/SA/Architect) ช่วยทำงานในแต่ละขั้น

## โครงสร้าง

```text
lek-vibe/            โปรเจกต์หลัก: ระบบเลขมงคลและทะเบียนรถมงคล (Next.js + PostgreSQL)
  .claude/skills/    Skill ที่ Claude Code ใช้เมื่อทำงานในโฟลเดอร์ lek-vibe/
skills/              สำเนา Skill สำหรับนำไปใช้กับโปรเจกต์อื่น
```

## โปรเจกต์ LekVibe

Web Application วิเคราะห์เบอร์มือถือและทะเบียนรถตามหลักเลขศาสตร์ มีระบบหลังบ้านสำหรับจัดการกฎ พร้อม Unit Test, API Test และ Playwright E2E

วิธีติดตั้ง รัน และทดสอบอยู่ใน [lek-vibe/README.md](lek-vibe/README.md) ส่วนสรุปของแต่ละ session (01–12) อยู่ใน [lek-vibe/docs/](lek-vibe/docs/)

## Claude Code Skills

| Skill | บทบาท | ใช้เมื่อ |
| --- | --- | --- |
| [user-story-reviewer](lek-vibe/.claude/skills/user-story-reviewer/SKILL.md) | Senior BA/SA/PO/QA | ตรวจ User Story หรือ Requirement เพื่อหา gap, ความกำกวม, Business Rule, Acceptance Criteria และ Edge Case |
| [system-analyst](lek-vibe/.claude/skills/system-analyst/SKILL.md) | System Analyst | แปลง Requirement เป็น Functional Spec, Data Model, API Contract, Test Plan และ NFR (ฉบับภาษาไทย) |
| [solution-architect](lek-vibe/.claude/skills/solution-architect/SKILL.md) | Solution Architect | วางสถาปัตยกรรม ประเมิน Trade-off และเขียน ADR |

Skill ใน `lek-vibe/.claude/skills/` จะทำงานเมื่อแก้ไฟล์ภายใน `lek-vibe/` เรียกใช้ได้ด้วยการพิมพ์ `/system-analyst` หรือขอให้ Claude ทำงานที่ตรงกับคำอธิบายของ Skill นั้น

ถ้าจะใช้ Skill กับโปรเจกต์อื่น ให้คัดลอกโฟลเดอร์ของ Skill ไปไว้ที่ `<project>/.claude/skills/` หรือที่ `~/.claude/skills/` ถ้าต้องการใช้ทุกโปรเจกต์

## ลำดับการทำงานใน Workshop

1. **User Story:** เขียน Story แล้วตรวจด้วย `user-story-reviewer`
2. **Requirement:** เขียน System Requirements (FR/BR/NFR) ด้วย `system-analyst`
3. **Design:** ทำ Architecture/ADR, Use Case, Sequence และ ERD ด้วย `solution-architect`
4. **Build:** พัฒนาเว็บด้วย Next.js และ PostgreSQL บน Docker
5. **Test:** ทำ Test Plan, Golden Cases, Playwright E2E และฝึกล่าบั๊กด้วย BUG_MODE
