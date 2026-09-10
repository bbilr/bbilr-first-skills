---
name: thai-clear-brief
description: Use when Codex needs to write, rewrite, teach, summarize, explain, translate into, or polish Thai so the result is concise, clear, easy to understand, natural, and not verbose. Trigger for Thai communication tasks that ask for brevity, plain language, key-point capture, short explanations, executive summaries, learning Thai usage, or reducing wordiness.
---

# Thai Clear Brief

Use this skill to produce Thai that is short, clear, natural, and useful. Prioritize meaning over decoration.

## Core Style

- Write in Thai unless the user asks otherwise.
- Lead with the answer, then add only necessary context.
- Use everyday Thai. Avoid bureaucratic, academic, or translated-sounding phrasing.
- Keep sentences short. Prefer one idea per sentence.
- Remove filler, repeated meaning, and ornamental words. Preserve uncertainty when evidence is incomplete; do not turn an inference into a fact for brevity.
- Preserve important nuance, intent, tone, names, numbers, dates, and constraints.
- Match formality to the user and situation. Do not over-formalize casual text.

## Quick Workflow

1. Identify the reader, purpose, and must-keep points.
2. Extract the core message in one sentence.
3. Rewrite with the fewest natural Thai words that keep the meaning intact.
4. Check for missing facts, unclear pronouns, and awkward translated Thai.
5. If helpful, provide a short note explaining the key language choice.

## Output Shapes

These shapes are optional. Prefer a direct paragraph when labels add no value. Preserve technical English terms, exact commands, paths, source links, numbers, and verification limitations.

For rewrites:

```text
ฉบับกระชับ:
...
```

For explanations:

```text
สรุปสั้นๆ:
...

จำง่ายๆ:
...
```

For learning Thai usage:

```text
ใช้แบบนี้:
...

เพราะว่า:
...

ตัวอย่าง:
...
```

## Editing Rules

- Prefer active, direct phrasing.
- Replace long connectors with simple ones: `เนื่องจาก` -> `เพราะ`, `อย่างไรก็ตาม` -> `แต่`, when tone allows.
- Convert abstract nouns into verbs when it sounds more natural.
- Use bullets only when they improve scanning.
- Avoid long introductions such as `จากข้อมูลดังกล่าวสามารถสรุปได้ว่า`.
- Avoid ending with generic offers unless the user asks for options or follow-up.

## Preserve Tone

- Friendly: warm, simple, human.
- Professional: clear, polite, restrained.
- Formal: respectful but still concise.
- Persuasive: specific benefit first, no hype.
- Instructional: step-by-step, no lecture.

## Quality Check

Before finalizing, ask internally:

- Is the main point visible in the first line?
- Can one sentence be split or deleted?
- Did any important fact disappear?
- Does it sound like a Thai person would actually write it?
- Is it shorter without becoming vague?
