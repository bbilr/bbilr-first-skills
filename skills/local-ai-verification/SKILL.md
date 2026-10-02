---
name: local-ai-verification
description: Verify local AI model files, dependencies, workflow execution, and generated artifacts. Use for ComfyUI or similar local inference setup, model compatibility checks, and image, audio, video, or TTS quality review; not for general AI news or remote-service recommendations.
---

# Local AI Verification

Verify the requested workflow and artifact, using the project's own acceptance criteria.

## Inspect Before Running

1. Find the actual workflow, runtime, model locations, versions, and relevant logs. Inspect workflow nodes and referenced APIs; do not infer installed support from a downloaded JSON file.
2. Read project-owned settings for model family, precision, adapters, strength, triggers, seeds, and quality thresholds. Record source and date where these may drift. Do not turn another project's settings into defaults.
3. Match required files and dependencies to the workflow. Check names, formats, or hashes where useful. A file's presence does not establish compatibility, provenance, or runtime success.
4. Use a small representative run within the authorized resource budget. Verify GPU/device use from runtime evidence if claiming a GPU test. Do not change the chosen model or download large replacements without a need within scope.

## Review The Output

- Inspect the actual image, audio, or video artifact. For video, check metadata and representative frames or playback appropriate to the requested behavior.
- For character consistency, apply project-approved, pose-aware identity criteria and visual review. A similarity score alone does not establish acceptable face, anatomy, outfit, or framing. If no usable face is visible, report the metric's limitation.
- Keep numerical checks and visual judgments separate. Report missing criteria instead of inventing thresholds.
- Preserve approved datasets, identity references, partial downloads, and checkpoints. Do not clean them up as a side effect of verification.

## Audio And TTS

- Identify the actual engine/version, voice/model, supported language, input text, and pronunciation settings. Reuse the project's selected voice and approved audio; do not silently replace them for a new experiment.
- Use a small representative sample covering relevant Thai text, proper nouns, numbers, mixed-language terms, or punctuation. Do not require cases absent from the requested output.
- Check decode success, duration, and audio metadata separately from listening. A transcript match or valid audio file does not establish correct pronunciation, naturalness, or acceptable sound.
- Listen when the host supports playback/review, checking omissions, repetitions, clipping, artifacts, pronunciation, and voice consistency as relevant. If listening is unavailable, explicitly report that audio quality was not listened to or verified.
- Keep experimental output separate from reviewed assets. Preserve batch progress and checkpoints so a retry can resume without overwriting accepted audio or regenerating completed items unnecessarily.
- Apply project-owned acceptance criteria. A passing sample does not prove consistency across a batch; user acceptance and technical checks are separate evidence.

## Report And Stop

Report the tested workflow/version, settings needed to reproduce the result, output paths, and failed or skipped checks. Distinguish `static-valid`, `dependencies-present`, `GPU-tested` or `CPU-tested`, and `output-reviewed`. Use `production-verified` only with explicit production acceptance evidence. Stop at the requested scope; a passing sample does not prove training completion or broad production quality.
