# Evidence First Skills

[ภาษาไทย](README.th.md)

Seven reusable agent skills for evidence-backed work, fewer repeated questions, and clear verification boundaries. Built from practical coding, setup, local AI, business reconciliation, and Thai communication workflows.

These are instructions, not background services. They do not add tools, bypass permissions, guarantee correctness, or automatically persist state across sessions.

## Skills

| Skill | Purpose | Example request |
| --- | --- | --- |
| [evidence-first-work](skills/evidence-first-work/SKILL.md) | Tie claims to evidence, honor settled decisions, verify and stop at the requested scope. | `Use $evidence-first-work to fix this bug and report the checks actually run.` |
| [repo-intake](skills/repo-intake/SKILL.md) | Understand an unfamiliar repository without unnecessary cloning or installation. | `Use $repo-intake to explain this repository and its supported setup.` |
| [install-checker](skills/install-checker/SKILL.md) | Separate global/project scope, installed files, discovery, and working execution. | `Use $install-checker to install this tool globally and verify what works.` |
| [local-ai-verification](skills/local-ai-verification/SKILL.md) | Check local model/workflow dependencies, execution, and actual output quality. | `Use $local-ai-verification to check this ComfyUI workflow against the project criteria.` |
| [business-reconciliation](skills/business-reconciliation/SKILL.md) | Reconcile orders, settlements, bank movements, and control totals without double counting. | `Use $business-reconciliation to reconcile these exports and list unmatched rows.` |
| [thai-clear-brief](skills/thai-clear-brief/SKILL.md) | Write natural, concise Thai while retaining uncertainty and technical detail. | `Use $thai-clear-brief to rewrite this explanation in clear Thai.` |
| [pordee](skills/pordee/SKILL.md) | Use a concise Thai style with lite/full/stop controls and honest statistics. | `Use $pordee in lite mode to summarize the result.` |

## Install For Codex On Windows

Prerequisites: Git and PowerShell. Run the following from a directory where you want the repository checkout. It uses `CODEX_HOME` when set, otherwise your user profile's `.codex` directory.

```powershell
git clone https://github.com/bbilr/evidence-first-skills.git
if ($LASTEXITCODE -ne 0) { throw 'Clone failed' }
Set-Location evidence-first-skills

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

Automatic selection is permitted by the supplied metadata but is not guaranteed on every request. For a default preference, review and merge the relevant rules from [AGENTS.example.md](AGENTS.example.md) into your existing Codex-home `AGENTS.md`. Do not overwrite unrelated instructions. Choose one main workflow and add only relevant domain/style guidance.

Keep project-specific paths, credentials, prices, fee rates, model settings, and identity thresholds in private project configuration. The public skills intentionally contain no personal project data.

## Update Or Remove

Use `git pull --ff-only` in the checkout, review the diff, and back up existing installed folders before copying a selected update. Do not blindly replace customized skills. To uninstall, remove only the corresponding installed skill folders and any preferences you added; confirm their exact paths first. Removing a checkout alone does not uninstall copied skills.

## Validation And Limitations

The initial release was checked with Codex's bundled `quick_validate.py` for all seven skills, YAML parsing, local Markdown link checks, and a public-file privacy scan. A disposable install-copy smoke test checked file layout and refusal to overwrite existing skills. These checks establish package structure, not improved behavior in every future task. Real GPU runs and business reconciliations are not included as evidence for this package.

## License And Scope

[MIT License](LICENSE). You may use, modify, and redistribute this package under its license. This release contains the seven skills listed above and an optional defaults example. It does not redistribute Ponytail, Superpowers, Compass Skills, Obsidian integrations, other installed plugins, private memories, or host configuration.
