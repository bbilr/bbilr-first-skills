# Compatibility And Migration / ความเข้ากันได้และการย้ายชุด

## One Workflow Owner / ใช้ workflow หลักชุดเดียว

`bbilr-first-skills` coordinates its seven companions. Domain tools and skills remain useful; multiple mandatory process owners are the source of conflict. An installed file is not proof that its rules are active, and changing config does not rewrite an already-loaded conversation.

ตัวหลักเลือกสกิลเฉพาะงานที่จำเป็น เครื่องมือด้านเกม การเงิน วิจัย และ Obsidian ยังใช้ร่วมกันได้ การติดตั้งไฟล์ไม่ใช่หลักฐานว่า session โหลดกฎแล้ว และการเปลี่ยน config ไม่ได้ล้างคำสั่งที่โหลดไปก่อนหน้า

| Conflict | Replacement / วิธีจัดการ |
| --- | --- |
| Load a skill at 1% relevance; multiple always-on routers | Select actual task fit through one main workflow / เลือกตามงานจริงผ่านตัวหลักเดียว |
| Design approval for every small edit | Ask only about material unresolved decisions / ถามเฉพาะเรื่องสำคัญที่ยังไม่ตกลง |
| Remove all hedging; unsupported token-saving claims | Preserve evidence-based uncertainty; use measured telemetry only / เก็บความไม่แน่ใจและใช้สถิติที่วัดได้ |
| Fixed test count, no frameworks/fixtures, or unconditional TDD | Reuse project tests and scale to risk / ใช้เครื่องมือเดิมและทดสอบตามความเสี่ยง |
| Ask again after the user delegates a routine choice | Decide within delegated scope / ตัดสินใจในขอบเขตที่มอบหมาย |
| Multiple copies of the same skill | Keep one intended version; archive the other outside skill discovery / เก็บเวอร์ชันที่ใช้จริงและย้ายสำเนาออกนอกโฟลเดอร์สกิล |

## Reference Migration / การย้ายชุดอ้างอิง

The maintainer's migration disables the installed Superpowers variants, Caveman, Ponytail, and HOTL plugins. It disables only Aegis's competing router and brevity skill, keeping other Aegis specialists available. Standalone Caveman and brainstorming copies are archived outside discovery. The installed Compass Task Clarifier is adapted locally and made explicit-only; that third-party file is not redistributed here.

ในการย้ายชุดของผู้ดูแล ปิด Superpowers ทั้งสองรายการ, Caveman, Ponytail และ HOTL; Aegis ปิดเฉพาะ router กับสกิลภาษาแบบย่อ ส่วนเฉพาะด้านยังอยู่ ย้าย Caveman และ brainstorming สำเนาเดี่ยวออกจากโฟลเดอร์สกิล ปรับ Task Clarifier ในเครื่องให้เรียกเมื่อขอโดยตรง และไม่แจกจ่ายไฟล์จากผู้พัฒนารายอื่นใน repo นี้

These are explicit migration choices, not actions performed by the README installer. For another setup, inspect exact installed names and versions first. Do not disable an unrelated domain plugin merely because it also recommends verification.

รายการนี้เป็นการปรับที่ตั้งใจทำ ไม่ใช่สิ่งที่คำสั่งติดตั้งทำอัตโนมัติ เครื่องอื่นต้องตรวจชื่อและเวอร์ชันจริงก่อน อย่าปิดสกิลเฉพาะด้านเพียงเพราะมีกฎตรวจหลักฐานเหมือนกัน

## Supported Controls / วิธีตั้งค่าที่รองรับ

Codex documents per-skill `[[skills.config]]` overrides and restarting after a configuration change in [Build skills](https://learn.chatgpt.com/docs/build-skills). Plugin enablement uses `plugins.<plugin>.enabled` as documented in the [Configuration Reference](https://learn.chatgpt.com/docs/config-file/config-reference). Match your actual plugin ID or skill path; do not copy another user's absolute paths.

ใช้การตั้งค่าเปิด/ปิดที่ Codex รองรับ และ restart หลังแก้ config จากนั้นตรวจรายการสกิลอีกครั้ง อย่าอ้างว่าเปลี่ยนแล้วทุก session เพียงเพราะไฟล์ config ผ่าน TOML parser

Back up configuration and standalone skills before migration. Keep backups outside public repositories and skill discovery. Restore only the specific setting or archived folder you intend to recover, preserving later user changes. Do not patch vendor cache files: updates can replace them. Path-specific skill exclusions may need updating after a plugin version change; recheck them when updating plugins. Trusted project settings can override plugin enablement, so verify the effective host/project state.

สำรอง config และสกิลก่อนย้าย เก็บนอก public repo และนอกโฟลเดอร์ที่ค้นสกิล กู้คืนเฉพาะรายการที่ต้องการโดยรักษาการแก้ไขใหม่ไว้ ไม่แก้ไฟล์ vendor cache เพราะอัปเดตอาจทับ การปิดสกิลตาม path ต้องตรวจใหม่เมื่อเวอร์ชัน plugin เปลี่ยน และค่า project อาจทับค่าเปิด/ปิดระดับผู้ใช้

## Scope Of Verification / ขอบเขตการตรวจ

Package validators and configuration parsing establish structure only. Verify catalog discovery in a fresh host session, then try a representative task. Neither this package nor a migration promises zero mistakes, automatic activation in all environments, or a measured reduction in token usage.

validator ยืนยันโครงสร้างเท่านั้น ต้องตรวจการค้นพบใน session ใหม่และทดลองงานจริง ชุดนี้ไม่รับประกันว่าจะไม่มีข้อผิดพลาด ใช้อัตโนมัติทุก environment หรือประหยัด token เป็นตัวเลขใด
