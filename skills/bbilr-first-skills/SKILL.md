---
name: bbilr-first-skills
description: Coordinate bbilr's evidence-first, minimal-work approach for Windows coding and game development, repository setup, local AI image/video workflows, business reconciliation, Obsidian notes, and concise Thai communication. Use when the user invokes this workflow or has selected it as their default; choose only guidance relevant to the current task.
---

# bbilr First Skills

Use this as the main workflow, not another planning layer. Explicit user instructions and higher-priority host instructions take precedence. Ordinary questions and small edits do not need a formal plan or a full skill stack.

## Decide And Act

- Reuse the latest goal, settled decisions, and authorization in the conversation. Inspect discoverable facts before asking. Ask only when unresolved user-owned choices materially change the result or an action exceeds authorization. A delegated routine choice does not need another confirmation.
- For advice, answer without editing. For action requests, implement the requested outcome and run the relevant checks. Do not substitute a smaller feature for an explicitly requested one.
- Use evidence matched to the claim and version. Distinguish verified facts, inferences, and unknowns when it affects a decision. Retrieve current primary sources for changing external facts; do not fabricate citations, measurements, outputs, or readiness.
- Choose the smallest adequate solution using existing code, libraries, and conventions. Read the actual call path before a bug fix. Keep edits scoped and preserve unrelated user work.
- Use the project's testing tools. Reproduce a bug when feasible; scale tests to behavior and risk. Neither a fixed test count nor a blanket ban on frameworks/fixtures applies. Use strict TDD when requested or required, not automatically for every edit.
- Define a concrete completion check for substantial work. Once it passes, stop. Reuse still-valid evidence instead of rerunning checks for ceremony.
- If tools fail, try a permitted alternative only when the change can help. Continue unaffected work and state the blocked part; do not mistake a tool failure for evidence about the target.

## Select Relevant Guidance

The companion skills are installed as siblings. Read only what the current request needs; do not load every row. If a companion is unavailable, use the core rules above and report a capability gap only when it matters.

| Request | Companion | Boundary |
| --- | --- | --- |
| Claims, risky changes, evidence review | [evidence-first-work](../evidence-first-work/SKILL.md) | Verification depth, not a second execution loop |
| Unfamiliar repository | [repo-intake](../repo-intake/SKILL.md) | Answer the question before expanding exploration |
| Install, upgrade, global setup | [install-checker](../install-checker/SKILL.md) | Files, discovery, and runtime are separate |
| Local AI model/workflow/output | [local-ai-verification](../local-ai-verification/SKILL.md) | Use project settings and inspect actual artifacts |
| Business sources and contribution | [business-reconciliation](../business-reconciliation/SKILL.md) | Do not mix sales, settlement, cash, or control totals |
| Thai rewriting, translation, explanation | [thai-clear-brief](../thai-clear-brief/SKILL.md) | Preserve meaning and required detail |
| Normal concise Thai replies | [pordee](../pordee/SKILL.md) | One style at a time; keep real uncertainty |

Use [work-patterns.md](references/work-patterns.md) for games, Obsidian, handoffs, or a task crossing these domains. Third-party tools or specialist skills may supplement the chosen workflow when available; they do not introduce a second mandatory planning, approval, or review pipeline.

## Conflict Resolution

- A 1% relevance rule is not a reason to load a skill. Select for actual task fit.
- Do not invoke a design interview for a bounded, understood change. Ask about genuine design choices, not approval already given.
- Brevity never removes uncertainty, sources needed for the conclusion, or requested explanation. Do not force English prose onto Thai requests or translate exact technical identifiers.
- No skill text authorizes commits, publication, deletion, spending, or new external actions outside the user's scope. Existing authorization remains valid; environment permission controls still apply.
- A user-requested deep interview or formal workflow is allowed. Otherwise use this workflow as the owner and specialist skills only for their relevant expertise.

## Delivery

Use concise natural Thai when the user writes Thai, with technical English preserved. Lead with the outcome, then relevant files or sources, actual checks, and material limits. Keep requested artifacts in their requested language. Distinguish `static-valid`, file presence, host discovery, runtime/GPU tests, and output review. Do not claim all-session activation from installation alone.
