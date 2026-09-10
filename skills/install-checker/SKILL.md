---
name: install-checker
description: Evidence-backed installation and setup workflow for GitHub tools, plugins, packages, CLIs, MCP servers, Unity/Godot packages, Python or Node projects, and global-vs-project installation decisions. Use when the user asks how to install, update, configure, run, uninstall, or make a tool available globally. Do not use for ordinary code edits unrelated to setup.
---

# Install Checker

Use this skill to make install instructions accurate and low-risk.

## Install Flow

1. Verify the current install instructions from primary sources: repo README, official docs, release notes, package registry, or local project docs.
2. Identify the target environment before giving commands: OS, shell, package manager, runtime versions, project type, and whether the user wants global or per-project setup.
3. Separate install surfaces:
   - global CLI/tool/runtime
   - per-project package or plugin
   - editor extension or engine package
   - MCP/server/client configuration
   - environment variables, credentials, or PATH changes
4. Prefer the official, simplest supported path. Avoid unofficial shortcuts unless clearly labeled and justified.
5. For commands, state what each command changes and where it writes.
6. Honor existing authorization for the requested installation and scope. Ask before additional spending, destructive replacement, publication, credential access, or configuration changes outside that scope. Never print credentials.
7. Verify after install with the smallest check: version command, package listing, config file readback, smoke test, or documented health check.

## Output

Give practical install steps only after verification:

- Recommended path: global, per-project, or both, with reason.
- Commands: OS/shell-specific and copy-ready.
- Verification: exact check to confirm it worked.
- Caveats: version, permissions, restart, project-specific package, secrets, or rollback notes.
- Sources: primary docs or local files used.

## Boundaries

- Do not invent install commands, package names, versions, URLs, config keys, or file paths.
- Do not assume a GitHub repo supports global install just because it is a CLI or plugin.
- A direct install request authorizes necessary installation within the stated scope; it does not authorize unrelated configuration changes or bypass environment permissions.
- If docs are stale, missing, or contradictory, say so and propose the smallest safe check.

## Discovery And Runtime Checks

- Inventory the existing installation and active configuration before adding another copy. Preserve unrelated settings and back up any file that must be replaced.
- For skills or plugins, report separately: files installed, host discovery confirmed, and actual invocation tested. A folder or valid frontmatter proves only the first stage.
- For MCP, distinguish client configuration, server startup, connection, and a representative tool call. Config readback alone is not an end-to-end test.
- State which user, host, environment, or project the installation covers. Global installation does not prove availability in every host, remote environment, already-running session, or project.
- Verify documented reload/restart requirements; if unavailable, report discovery as unverified instead of promising a restart will fix it.
- Verify destination contents and report the changed version or revision when available. Stop when the requested install and available checks are complete.
