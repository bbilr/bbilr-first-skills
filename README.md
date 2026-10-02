# bbilr First Skills

[ภาษาไทย](README.th.md)

One coordinating skill and eight focused companions for bbilr's working style: concise Thai with technical English, evidence before claims, minimal implementation, and no repeated approval inside an agreed scope. Covers Windows coding and game development, repository setup, source research, local AI image/audio/video workflows, business reconciliation, and Obsidian research notes.

Formerly `bbilr/evidence-first-skills`. The repository is renamed, not duplicated. Existing companion skill names remain compatible; the new entry point is `$bbilr-first-skills`.

These are instructions, not background services. They do not add tools, bypass permissions, guarantee correctness, or automatically persist state across sessions.

## Skills

| Skill | Purpose | Example request |
| --- | --- | --- |
| [bbilr-first-skills](skills/bbilr-first-skills/SKILL.md) | Select one workflow, preserve settled decisions, and apply the relevant domain guidance. | `Use $bbilr-first-skills to handle this task with evidence and concise Thai.` |
| [evidence-first-work](skills/evidence-first-work/SKILL.md) | Tie claims to evidence, honor settled decisions, verify and stop at the requested scope. | `Use $evidence-first-work to fix this bug and report the checks actually run.` |
| [repo-intake](skills/repo-intake/SKILL.md) | Understand a repository, adoption fit, and component licenses without unnecessary installation. | `Use $repo-intake to explain this repository and its supported setup.` |
| [source-research](skills/source-research/SKILL.md) | Collect multi-source evidence with dates, locators, scope, and unresolved gaps. | `Use $source-research to compare competitors with traceable sources and separate facts from inference.` |
| [install-checker](skills/install-checker/SKILL.md) | Separate global/project scope and verify installed-version compatibility, discovery, and execution. | `Use $install-checker to install this tool globally and verify what works.` |
| [local-ai-verification](skills/local-ai-verification/SKILL.md) | Check model/workflow dependencies and actual image, audio, video, or Thai TTS output. | `Use $local-ai-verification to check this Thai TTS sample and distinguish decode checks from listening.` |
| [business-reconciliation](skills/business-reconciliation/SKILL.md) | Reconcile business records without double counting; review OCR drafts before confirming totals. | `Use $business-reconciliation to reconcile these exports and list unmatched rows.` |
| [thai-clear-brief](skills/thai-clear-brief/SKILL.md) | Write natural, concise Thai while retaining uncertainty and technical detail. | `Use $thai-clear-brief to rewrite this explanation in clear Thai.` |
| [pordee](skills/pordee/SKILL.md) | Use a concise Thai style with lite/full/stop controls and honest statistics. | `Use $pordee in lite mode to summarize the result.` |

## Install For Codex On Windows

Prerequisites: Git and PowerShell. Run the following from a directory where you want the repository checkout. It uses `CODEX_HOME` when set, otherwise your user profile's `.codex` directory.

```powershell
git clone https://github.com/bbilr/bbilr-first-skills.git
if ($LASTEXITCODE -ne 0) { throw 'Clone failed' }
Set-Location bbilr-first-skills

$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
$destination = Join-Path $skillHome 'skills'
$selected = @(Get-ChildItem -LiteralPath ./skills -Directory)
# To install only selected skills, replace the line above, for example:
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

The command installs per-user skill files, not machine-wide services or project dependencies. For other operating systems, copy the selected skill folders to the active Codex home's `skills` directory using your normal file tools. Other agents may support `SKILL.md`, but their discovery paths and invocation syntax must be checked separately; `agents/openai.yaml` is Codex-specific metadata.

## Verify And Use

1. Check that each installed folder contains `SKILL.md` and `agents/openai.yaml`.
2. In a new Codex session, check whether the skill appears in the available skill list. If absent, verify the active Codex home and host-specific reload behavior. A new session alone is not proof of discovery.
3. Invoke a skill explicitly with an example above and inspect whether its guidance was actually applied. Files present, discovery, and successful use are separate checks.

Automatic selection is permitted by the supplied metadata but is not guaranteed on every request. To use this as your main workflow, review and merge [AGENTS.example.md](AGENTS.example.md) into your existing Codex-home `AGENTS.md`. Do not overwrite unrelated instructions. The main skill selects companions; it does not load all of them on every turn. Use Pordee for normal brief Thai and Thai Clear Brief for language-editing tasks.

See [Compatibility And Migration](COMPATIBILITY.md) for conflicting workflow categories, the reference migration, and how to avoid reintroducing duplicate routers. Installation copies skills only: it does not disable other plugins, rewrite global instructions, or migrate an existing setup without your explicit action.

Keep project-specific paths, credentials, prices, fee rates, model settings, and identity thresholds in private project configuration. The public skills intentionally contain no personal project data.

## Update Or Remove

Use `git pull --ff-only` in the checkout, review the diff, and back up existing installed folders before copying a selected update. Do not blindly replace customized skills. To uninstall, remove only the corresponding installed skill folders and any preferences you added; confirm their exact paths first. Removing a checkout alone does not uninstall copied skills.

For an existing checkout of the old repository, update its remote with `git remote set-url origin https://github.com/bbilr/bbilr-first-skills.git`, then pull. Existing installed companion folders do not need a name change. Install the new `bbilr-first-skills` folder and merge the new defaults to adopt the coordinating workflow; review changes before replacing any customized companion.

## Validation And Limitations

The current package is checked with Codex's bundled `quick_validate.py` for all nine skills, YAML parsing, local Markdown link checks, and a public-file privacy scan. A disposable install-copy smoke test checks file layout and refusal to overwrite existing skills. These checks establish package structure, not improved behavior in every future task. Research extraction, OCR, GPU runs, TTS listening, video rendering, and business reconciliations are not runtime acceptance evidence for this package. Host discovery and actual invocation are separate checks.

## Research And Media Guidance

Use `$source-research` for multi-source comparisons, competitor or customer-pain research, and source audits. A single fact lookup does not need an extra research workflow. Crawl4AI and Docling are optional tool references, not bundled dependencies or automatic installations. Repository popularity and generated business ideas are leads, not proof of paid demand or profit.

For video requests, [video-work.md](skills/bbilr-first-skills/references/video-work.md) supplements an available specialist such as Hyperframes. It reuses the approved project brief and checks rendered Thai text, framing, timing, and audio rather than adding another mandatory interview. Keep voices and quality thresholds in project-owned sources.

## License And Scope

[MIT License](LICENSE). You may use, modify, and redistribute this package under its license. This release contains the nine skills listed above, work-pattern/video guidance, and optional defaults. It does not redistribute Ponytail, Superpowers, Compass Skills, Obsidian integrations, other installed plugins, private memories, or host configuration. Shared principles are expressed in this package's own instructions; third-party packages retain their own ownership and licenses.
