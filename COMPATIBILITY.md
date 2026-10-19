# Compatibility And Migration / การย้ายชุด

## Current Package / ชุดปัจจุบัน

Five skills: bbilr-first-skills, install-checker, local-ai-verification, business-reconciliation, and the separately licensed task-observer adaptation. AGENTS.md owns general work rules. Optional external specialists are not bundled.

มี 5 สกิลตาม README ให้ AGENTS.md ดูแลกฎทั่วไป สกิลเสริมเฉพาะงาน ไม่ต้องโหลดทุกตัว

## Migration / วิธีปรับชุดเดิม

1. Back up the exact installed folders and configuration outside skill discovery and public Git repositories. Verify backup contents before removal.
2. Review local customizations in repo-intake and source-research; their compact source/adoption checks now live in bbilr-first-skills.
3. Remove only the approved installed copies of repo-intake, source-research and, if adopting the maintainer's configuration, find-skills. Updating this checkout does not uninstall them.
4. Merge the main skill update; remove stale references to retired skills.
5. Install the Task Observer adaptation with allow_implicit_invocation=false. Do not add always-on activation or scheduling. A review may propose changes, not automatically apply them.
6. If adopting the maintainer's design setup, disable the exact Universal Design Principles plugin through supported host settings. Keep Impeccable as the optional frontend specialist and use other platform specialists only when relevant.
7. Reload as required by the host and inspect effective skill discovery. Project-level settings and old conversations may retain different state.

สำรองและตรวจไฟล์ก่อนถอน รวมกฎที่ปรับเองก่อนเปลี่ยนตัวหลัก task-observer เรียกเฉพาะเมื่อขอทบทวน การติดตั้งไม่ปิดปลั๊กอินหรือถอนสกิลอื่นให้เอง ต้องตรวจสถานะจริงหลังโหลดใหม่

## Recovery And Updates / กู้คืนและอัปเดต

Restore only the intended backed-up folder or setting after comparing later edits. Do not replace an entire current config to undo one plugin flag. Do not modify managed plugin caches. Stage upstream updates and preserve local boundaries before installing.

กู้คืนเฉพาะรายการที่ต้องการ รักษาการแก้ไขใหม่ ไม่ทับ config ทั้งไฟล์เพื่อเปิดปลั๊กอินตัวเดียว และไม่แก้ vendor cache

The public observer asks adopters to select a private durable directory outside skill discovery; local maintainer paths are not shipped. No private memory, logs, configuration or backups are included.

ฉบับสาธารณะไม่ระบุพาธส่วนตัว ไม่รวม memory, log, config หรือสำรองของผู้ดูแล

## Evidence Limits / ข้อจำกัด

Static validation, YAML policy checks and link checks establish package structure only. They do not prove runtime quality, improved reasoning, automatic activation or token savings. A separate CLI/runtime bundled by an external specialist remains outside this package.

การตรวจไฟล์ไม่ยืนยันคุณภาพงานหรือความแม่นยำของโมเดล ต้องทดสอบงานจริงแยกกัน
