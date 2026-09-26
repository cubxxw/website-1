---
name: add-or-update-blog-post-zh-cn
description: Workflow command scaffold for add-or-update-blog-post-zh-cn in website-1.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /add-or-update-blog-post-zh-cn

Use this workflow when working on **add-or-update-blog-post-zh-cn** in `website-1`.

## Goal

Add or update blog posts in the Chinese (zh-cn) localization, often for new releases or spotlights.

## Common Files

- `content/zh-cn/blog/_posts/**/*.md`
- `content/zh-cn/blog/_posts/**/*.svg`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Translate or write the new blog post content.
- Add or update files under zh-cn/blog/_posts/ with appropriate naming.
- Include any related assets (e.g., SVGs) as needed.
- Commit with a message referencing the new post or update.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.