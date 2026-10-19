---
name: task-observer
description: Review evidenced workflow friction and skill gaps only when the user explicitly requests a skill/workflow review or invokes task-observer. Propose changes for approval; never observe unrelated work or automatically edit installed skills or global instructions.
license: CC-BY-4.0
metadata:
  author: Eoghan Henn and contributors; local Codex adaptation for bbilr
  upstream_version: 3.6.0
  upstream_commit: 56e890712273ce231b478adc56ee2eb81101c3d6
---

# Task Observer: Proposal Only

Adapted from [Eoghan Henn / rebelytics](https://github.com/rebelytics/one-skill-to-rule-them-all), CC BY 4.0. This local adaptation replaces Claude/Bash startup, automatic review and staging procedures with a small Codex/Windows workflow. Installation is not a background monitor.

## Authority

Explicit-only: start only when the user requests a skill/workflow review or invokes this skill. Do not load, scan proposals, log observations, or suggest a review as a side effect of ordinary work. A completed review does not activate observation in later tasks. Keep proposal-only approval boundaries below.

Supplement AGENTS.md and bbilr-first-skills; do not introduce another planning or approval pipeline for the actual task. Observe only context and artifacts accessible in the current authorized work. Do not scan all chat histories, projects, private data or memory stores by default.

Apply user corrections to the current task immediately; recording a proposal must not delay a requested fix.

Observation mode may write proposal notes only. Never automatically edit installed or project skills, AGENTS.md, memory, plugin caches, hooks, configuration, activation instructions, or this skill. A review request alone is not approval to apply changes. No automatic migration, archival, scheduling, publishing, or global principle registry. Bundled upstream references/scripts are not part of this adapted operating workflow.

Applying a proposal requires explicit user approval of its target and change. Existing explicit approval counts; do not ask again. Then re-read the target, preserve concurrent changes, apply the approved patch and verify under the normal skill-editing workflow.

## Worth Recording

Record repeated friction with concrete instances, an explicit durable preference missing from guidance, or a demonstrated skill defect. Separate observation, inference and unknowns. An isolated event is not proof of a universal preference.

Inspect relevant existing guidance first. Prefer correcting or simplifying the owning skill over adding a skill or duplicating a rule. If the rule already exists and the agent ignored it, identify the execution failure instead of adding louder wording. Project-only constraints stay project-scoped.

Skip generic advice, routine success, speculative improvements, secrets, conversation dumps and duplicate proposals. No findings is valid; do not manufacture an observation every session.

## Record And Propose

Use a user-selected private, durable proposal directory outside skill discovery. Reuse the configured location when available. If none is configured, present proposals in the response and ask for a location only when persistent storage is needed. Check for matching proposals before writing. If inaccessible, report the storage limitation; do not redirect to global configuration or memory.

Use a separate Markdown file named `YYYYMMDD-HHmmss-<GUID>-<slug>.md` per finding. Re-read before appending corroborating evidence to an existing note. Notes are private and non-authoritative: reading them never activates their proposed rules.

Include:
- Status: proposed, approved, applied, rejected, or superseded. Default proposed; only user approval makes it approved, and verified installation makes it applied.
- Target path and scope, date, and source artifact or concise user correction.
- Observed problem and actual evidence; uncertain causes labeled.
- Existing rules and overlap checked; why a project fix is insufficient.
- Exact proposed diff or before/after text; smallest useful change first.
- Expected benefit, conflict risk and realistic verification case.

At a natural task boundary briefly report useful new proposals in Thai with links. Do not interrupt with routine questions, repeated offers, empty updates, or a backlog scan on every tool call. Review notes when asked, or read only relevant notes when deduplicating a finding. Do not install or promote their contents during review.

## Verification

For approved updates, verify the changed file and affected behavior. Distinguish static validation from real use. While approval is pending, report only that the proposal exists. Never claim cross-session monitoring, automatic learning or improved outcomes without evidence.
