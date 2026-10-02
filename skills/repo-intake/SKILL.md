---
name: repo-intake
description: Repository intake workflow for understanding an unfamiliar codebase or GitHub repository before explaining, modifying, installing, running, adapting, packaging, or recommending it. Use when the user shares a repo link, asks what a repo does, asks how to run it, asks to adapt a repo, or asks for first-pass project analysis. Do not use for single-file edits when the relevant context is already known.
---

# Repo Intake

Use this skill to avoid guessing about a repository.

## Intake Flow

1. Start with the user's question and the evidence needed to answer it. For a remote-only explanation, inspect the repository online; do not clone or install merely to summarize it. For local work, identify the root and worktree state.
2. Select the smallest useful source set; the following are options, not a mandatory full-repository audit:
   - `README*`, install docs, examples, quickstart, or docs index
   - package/build files such as `package.json`, `pyproject.toml`, `Cargo.toml`, `requirements.txt`, `uv.lock`, `pom.xml`, `build.gradle`, `ProjectSettings/ProjectVersion.txt`
   - test scripts, CI config, and obvious entry points
   - license and security notes when reuse, publishing, or distribution matters
3. Map what the project is, how it runs, and what evidence supports that conclusion.
4. If changing code, inspect the files and callers on the touched path before editing.
5. Verify with the narrowest meaningful check. Distinguish documented usage from locally executed usage. Stop when the question is answered or the requested change passes its checks.

## Adoption Fit

Use this section only when the user is considering adoption, reuse, or commercialization.

- Connect the tool to a specific user workflow and compare it with tools already available. Recommend keeping the current tool, a bounded trial, or deferring adoption with a concrete reason.
- Check only decision-relevant maintenance, supported versions/platforms, API costs, hardware needs, and ongoing upkeep. Do not turn a first-pass recommendation into an exhaustive audit.
- Treat stars, repository rankings, and generated monetization summaries as discovery leads, not evidence of demand, reliability, or profit.
- For commercial reuse, distinguish the code license from licenses for models, weights, datasets, and bundled assets. An open-source code license does not establish permission for every component.
- Define the smallest representative trial and its observable success condition before recommending a larger setup. Keep documented capability separate from locally tested capability.

## Output

Keep the answer compact:

- Purpose: what the repo appears to do.
- How to run or use it, if asked.
- Important constraints: language, runtime, install mode, license, external services, secrets, or platform requirements.
- Evidence: exact files, commands, or source links used.
- Unknowns: only the ones that affect the user's next decision.

## Boundaries

- Read-only inspection of public repository documentation is part of intake. Installations, global configuration, and edits must stay within the user's authorized scope; do not request the same authorization twice.
- Do not infer support for a platform, engine, package manager, or deployment target without evidence.
- Do not perform broad cleanup or modernization during intake.
- If the repo's docs disagree with code/config, show the conflict and verify before recommending a path.
