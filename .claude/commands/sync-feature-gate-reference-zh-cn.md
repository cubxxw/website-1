---
name: sync-feature-gate-reference-zh-cn
description: Workflow command scaffold for sync-feature-gate-reference-zh-cn in website-1.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /sync-feature-gate-reference-zh-cn

Use this workflow when working on **sync-feature-gate-reference-zh-cn** in `website-1`.

## Goal

Synchronize or add new feature gate documentation in the Chinese (zh-cn) reference for command-line tools.

## Common Files

- `content/zh-cn/docs/reference/command-line-tools-reference/feature-gates/*.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify new or updated feature gates in the upstream documentation.
- Create or update corresponding .md files under zh-cn/docs/reference/command-line-tools-reference/feature-gates/
- Commit with a message indicating sync or add for the relevant feature gates.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.