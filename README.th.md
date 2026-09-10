# bbilr First Skills

[English](README.md)

สกิลหลัก 1 ตัวกับสกิลเฉพาะงาน 7 ตัว จัดตามวิธีทำงานของ bbilr: ภาษาไทยกระชับ เก็บ technical English ตรวจหลักฐานก่อนสรุป ทำเท่าที่จำเป็น และไม่ถามอนุมัติซ้ำในขอบเขตเดิม ครอบคลุมโค้ดและเกมบน Windows การติดตั้ง repo งาน local AI ภาพ/วิดีโอ กระทบยอดธุรกิจ และบันทึกวิจัยใน Obsidian

เปลี่ยนชื่อจาก `bbilr/evidence-first-skills` โดยใช้ repository เดิม สกิลย่อยยังใช้ชื่อเดิมได้ เพิ่ม `$bbilr-first-skills` เป็นจุดเริ่มต้นสำหรับเลือก workflow

สกิลเป็นชุดคำแนะนำ ไม่ใช่บริการที่ทำงานเบื้องหลัง ไม่ได้เพิ่มเครื่องมือ ข้ามสิทธิ์ รับประกันความถูกต้อง หรือบันทึกสถานะข้าม session ด้วยตัวเอง

## มีอะไรบ้าง

| สกิล | ใช้ทำอะไร | ตัวอย่างคำสั่ง |
| --- | --- | --- |
| [bbilr-first-skills](skills/bbilr-first-skills/SKILL.md) | เลือก workflow เดียว รักษาข้อสรุปเดิม และใช้สกิลเฉพาะที่งานต้องการ | `ใช้ $bbilr-first-skills ทำงานนี้จากหลักฐานและตอบไทยกระชับ` |
| [evidence-first-work](skills/evidence-first-work/SKILL.md) | ตรวจหลักฐาน เคารพข้อสรุปเดิม และทำงานจนผ่านเกณฑ์ที่ขอ | `ใช้ $evidence-first-work แก้บั๊กนี้ พร้อมบอกผลตรวจที่รันจริง` |
| [repo-intake](skills/repo-intake/SKILL.md) | อ่าน repo ใหม่เท่าที่จำเป็น ก่อนอธิบายหรือแก้โค้ด | `ใช้ $repo-intake ดูว่า repo นี้ทำอะไรและติดตั้งแบบไหนได้` |
| [install-checker](skills/install-checker/SKILL.md) | แยก global/project และตรวจว่าติดตั้งแล้ว ระบบพบแล้ว หรือใช้ได้จริง | `ใช้ $install-checker ติดตั้งเครื่องมือนี้แบบ global และตรวจผล` |
| [local-ai-verification](skills/local-ai-verification/SKILL.md) | ตรวจ model, dependency, workflow และ output จริง | `ใช้ $local-ai-verification ตรวจ ComfyUI workflow นี้ตามเกณฑ์โครงการ` |
| [business-reconciliation](skills/business-reconciliation/SKILL.md) | กระทบยอด order, settlement และ bank โดยไม่บวกยอดซ้ำ | `ใช้ $business-reconciliation กระทบยอดไฟล์เหล่านี้ แยกรายการที่ยังจับคู่ไม่ได้` |
| [thai-clear-brief](skills/thai-clear-brief/SKILL.md) | เขียนไทยให้ชัด กระชับ เก็บศัพท์เทคนิคและความไม่แน่ใจที่จำเป็น | `ใช้ $thai-clear-brief เรียบเรียงข้อความนี้ให้อ่านง่าย` |
| [pordee](skills/pordee/SKILL.md) | โหมดภาษาไทยกระชับ เลือก lite/full หรือหยุดได้ | `ใช้ $pordee แบบ lite สรุปผลนี้` |

## ติดตั้งใน Codex บน Windows

ต้องมี Git และ PowerShell รันจากโฟลเดอร์ที่ต้องการเก็บ repository คำสั่งใช้ `CODEX_HOME` ถ้าตั้งไว้ ไม่เช่นนั้นใช้ `.codex` ใน user profile

```powershell
git clone https://github.com/bbilr/bbilr-first-skills.git
if ($LASTEXITCODE -ne 0) { throw 'Clone failed' }
Set-Location bbilr-first-skills

$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
$destination = Join-Path $skillHome 'skills'
$selected = @(Get-ChildItem -LiteralPath ./skills -Directory)
# ถ้าต้องการแค่บางตัว ให้แทนบรรทัดด้านบน เช่น:
# $selected = @(Get-Item ./skills/evidence-first-work, ./skills/install-checker)

$ErrorActionPreference = 'Stop'
foreach ($skill in $selected) {
    if (Test-Path -LiteralPath (Join-Path $destination $skill.Name)) {
        throw "Already installed: $($skill.Name). Review and back up before updating."
    }
}
New-Item -ItemType Directory -Force -Path $destination | Out-Null
foreach ($skill in $selected) {
    Copy-Item -LiteralPath $skill.FullName -Destination $destination -Recurse
}
```

คำสั่งจะหยุดก่อนคัดลอกถ้ามีชื่อสกิลซ้ำ เพื่อให้ตรวจและสำรองของเดิมก่อนอัปเดต ติดตั้งระดับผู้ใช้ ไม่ได้ติดตั้ง dependency ของโครงการหรือทำให้ใช้ได้บนทุกเครื่องอัตโนมัติ

ระบบปฏิบัติการอื่นให้คัดลอกโฟลเดอร์สกิลที่เลือกไปยัง `skills` ใน Codex home ที่ใช้งานจริง ส่วน agent อื่นต้องตรวจ path และรูปแบบเรียกสกิลของระบบนั้นเอง ไฟล์ `agents/openai.yaml` เป็น metadata สำหรับ Codex

## ตรวจและเริ่มใช้

1. ตรวจว่าโฟลเดอร์ที่ติดตั้งมี `SKILL.md` และ `agents/openai.yaml`
2. เปิด session ใหม่ แล้วตรวจรายการสกิลที่ระบบพบ ถ้าไม่พบ ให้ตรวจ Codex home และวิธี reload ของ host การเปิด session ใหม่อย่างเดียวไม่ได้พิสูจน์ว่าพบสกิลแล้ว
3. เรียกสกิลตามตัวอย่างในตาราง และดูว่า agent ใช้แนวทางนั้นจริง แยกผลว่าไฟล์มีแล้ว ระบบพบแล้ว หรือทดลองใช้แล้ว

metadata อนุญาตให้เลือกสกิลอัตโนมัติ แต่ไม่ได้รับประกันว่าจะถูกเลือกทุกคำขอ หากต้องการใช้เป็น workflow หลัก ให้รวมกฎจาก [AGENTS.example.md](AGENTS.example.md) ใน `AGENTS.md` เดิม โดยรักษากฎอื่นไว้ สกิลหลักเลือกใช้เฉพาะส่วนที่เกี่ยวข้อง ใช้ Pordee สำหรับคำตอบไทยสั้นทั่วไป และ Thai Clear Brief สำหรับงานเรียบเรียงภาษา

ดู [ความเข้ากันได้และการย้ายชุด](COMPATIBILITY.md) สำหรับวิธีจัดการ workflow ที่ชนกัน คำสั่งติดตั้งคัดลอกสกิลเท่านั้น ไม่ปิด plugin อื่นหรือเขียนทับ global defaults อัตโนมัติ

path โครงการ ราคา ค่าธรรมเนียม credential รุ่นโมเดล ค่า LoRA และเกณฑ์ identity ให้เก็บในเอกสารโครงการส่วนตัว สกิลสาธารณะชุดนี้ไม่บรรจุข้อมูลส่วนตัวของโครงการ

## อัปเดตและถอนการติดตั้ง

รัน `git pull --ff-only` ใน repository ตรวจ diff และสำรองโฟลเดอร์สกิลที่ติดตั้งก่อนคัดลอกเวอร์ชันใหม่ อย่าทับสกิลที่ปรับเองโดยไม่ตรวจ หากถอนการติดตั้ง ให้ตรวจ path แล้วลบเฉพาะโฟลเดอร์สกิลที่ต้องการ พร้อมกฎอ้างอิงที่เพิ่มเอง การลบ repository ที่ clone มาไม่ได้ถอนสำเนาสกิลที่ติดตั้งไว้

ถ้ามี checkout ชื่อเก่า ให้รัน `git remote set-url origin https://github.com/bbilr/bbilr-first-skills.git` แล้ว pull สกิลย่อยเดิมไม่ต้องเปลี่ยนชื่อ เพิ่มโฟลเดอร์สกิล `bbilr-first-skills` และรวม defaults ใหม่เพื่อใช้ตัวหลัก ตรวจ diff ก่อนอัปเดตสกิลที่แก้เอง

## ตรวจสอบแล้วแค่ไหน

ชุดที่เปลี่ยนชื่อมีสกิล 8 ตัว ตรวจด้วย `quick_validate.py` ที่มากับ Codex รวมถึง parse YAML ตรวจลิงก์ Markdown ภายใน และสแกนข้อมูลส่วนตัวก่อนเผยแพร่ ทดลองขั้นตอนคัดลอกในโฟลเดอร์ชั่วคราวและตรวจว่าหยุดเมื่อชื่อสกิลซ้ำ

ผลเหล่านี้ยืนยันโครงสร้างแพ็กเกจ ไม่ได้รับประกันพฤติกรรมทุกงาน ยังไม่ได้ใช้การรัน GPU หรือกระทบยอดธุรกิจจริงเป็นหลักฐานรับรองแพ็กเกจนี้

## สิทธิ์การใช้และขอบเขต

ใช้ [MIT License](LICENSE) นำไปใช้ แก้ไข และแจกจ่ายต่อได้ตามเงื่อนไขในไฟล์ license

ชุดนี้มีสกิล 8 ตัวในตาราง แนวทางตามลักษณะงาน และตัวอย่างกฎ ไม่แจกจ่าย Ponytail, Superpowers, Compass Skills, Obsidian integration หรือ plugin ของผู้อื่น รวมถึงไม่เผยแพร่ memory ส่วนตัวหรือ config ของเครื่อง หลักการร่วมถูกเรียบเรียงเป็นคำแนะนำของชุดนี้เอง
