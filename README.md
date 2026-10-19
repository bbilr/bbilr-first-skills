# bbilr First Skills

[ภาษาไทย](README.th.md)

A small, Thai-first skill set for Windows-based coding, game projects, local AI verification and business reconciliation. General execution, approvals and delivery belong in your AGENTS.md; this package adds focused checks and selects relevant specialists instead of another mandatory planning workflow.

## Included Skills

| Skill | Actual use |
| --- | --- |
| [bbilr-first-skills](skills/bbilr-first-skills/SKILL.md) | Compact source/adoption checks and specialist selection. |
| [install-checker](skills/install-checker/SKILL.md) | Separate installation scope, file presence, host discovery and tested execution. |
| [local-ai-verification](skills/local-ai-verification/SKILL.md) | Verify actual image/audio/video output, including Thai TTS; preserve project settings and batch progress. |
| [business-reconciliation](skills/business-reconciliation/SKILL.md) | Keep sales, settlements and bank cash distinct; avoid duplicate revenue. |
| [task-observer](skills/task-observer/SKILL.md) | Explicitly requested workflow/skill review. Propose a patch; apply only after approval. No background observation. |

Use ordinary model capabilities for planning, repository explanations, source research and skill discovery. The former standalone repo-intake and source-research instructions are consolidated into the main skill. Find Skills is not bundled or required.

## Install And Use

From a new checkout, run in PowerShell:

```powershell
git clone https://github.com/bbilr/bbilr-first-skills.git
if ($LASTEXITCODE -ne 0) { throw 'Clone failed' }
Set-Location bbilr-first-skills
$ErrorActionPreference = 'Stop'
$skillHome = if ($env:CODEX_HOME) { $env:CODEX_HOME } else { Join-Path $env:USERPROFILE '.codex' }
$destination = Join-Path $skillHome 'skills'
$selected = @(Get-ChildItem -LiteralPath ./skills -Directory)
foreach ($skill in $selected) {
    if (Test-Path -LiteralPath (Join-Path $destination $skill.Name)) {
        throw "Already installed: $($skill.Name). Back up and review before updating."
    }
}
New-Item -ItemType Directory -Force -Path $destination | Out-Null
foreach ($skill in $selected) {
    Copy-Item -LiteralPath $skill.FullName -Destination $destination -Recurse
}
```

This installs user-level instructions only. It does not install runtimes, modify global configuration, remove old skills or disable plugins. Check the next session's skill list; file presence alone is not discovery or successful use.

Examples:
- `Use $install-checker to verify this Windows installation.`
- `Use $local-ai-verification to check this Thai TTS output.`
- `Use $task-observer to review recurring problems and propose changes without applying them.`

Task Observer has `allow_implicit_invocation: false`. It runs only on explicit review requests/invocation, never as a side effect of normal work, and requires approval before applying proposed skill changes. Other hosts must enforce the same boundary through their supported controls.

## Optional Specialists

Impeccable, bbilr-writing and session-handoff-prompt are optional, separately installed specialists referenced by name, not bundled dependencies. Preserve existing design and palette; do not stack multiple general design workflows. No automatic installation occurs when an optional skill is unavailable.

The maintainer's lean configuration disables Universal Design Principles and removes Find Skills, repo-intake and source-research from discovery. This is a documented migration choice, not a command this package executes. See [migration and recovery](COMPATIBILITY.md).

## Updates, Privacy And Limits

The second cleanup retires the generic studio-gate-check and dialogue-pipeline skills. A small [dialogue template](skills/bbilr-first-skills/references/dialogue-template.md) preserves the useful planning fields. The maintainer disabled MuAPI's Generative Media Skills and Unity Agent Workflows globally; Stark remains available for specific platform gaps. [Specialist compatibility](skills/bbilr-first-skills/references/specialist-compatibility.md) overrides Chinese-only report defaults and redundant approval prompts while preserving scope and host permissions. These are user-owned instructions, not vendor cache edits; installing this repository does not change plugin settings automatically.

Back up customized installed folders outside skill discovery before updates. Review changes and copy only the intended files; do not overwrite later edits. Merge the small [AGENTS example](AGENTS.example.md) into existing instructions only if useful.

Do not publish private paths, credentials, observations, memory or host configuration. The public Task Observer uses an adopter-selected storage directory instead of the maintainer's private path.

Package validation checks structure, metadata and local links. It does not demonstrate improved model accuracy, lower token use, successful GPU execution, audio quality or reliable behavior in every future session. These skills are instructions, not a background service or an additional model.

## Licenses

Original package content is [MIT](LICENSE). The adapted Task Observer is separately licensed [CC BY 4.0](skills/task-observer/LICENSE.txt), credited to Eoghan Henn and contributors, from [rebelytics/one-skill-to-rule-them-all](https://github.com/rebelytics/one-skill-to-rule-them-all), upstream 3.6.0 at `56e890712273ce231b478adc56ee2eb81101c3d6`. The adaptation removes automatic observation/startup/review scripts and adds explicit-only Codex metadata and proposal-only boundaries. The root MIT license does not relicense that component.

Formerly bbilr/evidence-first-skills; this remains the same renamed repository.
