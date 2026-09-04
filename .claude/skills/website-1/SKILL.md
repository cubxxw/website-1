```markdown
# website-1 Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides a comprehensive guide to the development patterns, coding conventions, and common workflows used in the `website-1` repository. The project is written in TypeScript, with a focus on content localization (notably Chinese and Vietnamese), reference documentation, and glossary management. This guide will help contributors maintain consistency and efficiency when adding features, updating documentation, or localizing content.

## Coding Conventions

### File Naming
- Use **kebab-case** for all file names.
  - Example: `feature-gates-list.md`, `my-component.ts`

### Import Style
- Use **relative imports** for modules within the project.
  - Example:
    ```typescript
    import { myFunction } from './utils/my-function';
    ```

### Export Style
- Prefer **named exports**.
  - Example:
    ```typescript
    // utils/my-function.ts
    export function myFunction() { /* ... */ }
    ```

### Commit Message Patterns
- Commit messages are freeform, but often use language prefixes such as `[vi]` or `[zh]` to indicate localization.
  - Example: `[zh] Sync feature gates for v1.28`

## Workflows

### sync-feature-gate-reference-zh-cn
**Trigger:** When a new feature gate is added or updated upstream and needs to be reflected in the zh-cn docs  
**Command:** `/sync-feature-gates-zh-cn`

1. Identify new or updated feature gates in the upstream documentation.
2. Create or update corresponding `.md` files under `content/zh-cn/docs/reference/command-line-tools-reference/feature-gates/`.
3. Commit with a message indicating sync or add for the relevant feature gates.

**Example:**
```bash
# Add a new feature gate translation
cp upstream/feature-gates/new-feature.md content/zh-cn/docs/reference/command-line-tools-reference/feature-gates/
git add content/zh-cn/docs/reference/command-line-tools-reference/feature-gates/new-feature.md
git commit -m "[zh] Sync feature gate: new-feature"
git push
```

---

### add-or-update-blog-post-zh-cn
**Trigger:** When a new blog post is published upstream or a translation/update is needed for zh-cn  
**Command:** `/add-blog-zh-cn`

1. Translate or write the new blog post content.
2. Add or update files under `content/zh-cn/blog/_posts/` with appropriate naming.
3. Include any related assets (e.g., SVGs) as needed.
4. Commit with a message referencing the new post or update.

**Example:**
```bash
# Add a new blog post translation
cp upstream/blog/new-release.md content/zh-cn/blog/_posts/2024-06-01-new-release.md
git add content/zh-cn/blog/_posts/2024-06-01-new-release.md
git commit -m "[zh] Add blog post: new-release"
git push
```

---

### update-generated-reference-en
**Trigger:** When a new Kubernetes version is released and generated reference docs need to be updated  
**Command:** `/update-reference-en`

1. Regenerate reference documentation for the new version.
2. Replace or update multiple `.md` files under reference directories:
    - `content/en/docs/reference/config-api/*.md`
    - `content/en/docs/reference/kubernetes-api/**/*.md`
    - `content/en/docs/reference/kubectl/generated/**/*.md`
    - `content/en/docs/reference/setup-tools/kubeadm/generated/**/*.md`
3. Commit all updated files with a message referencing the new version.

**Example:**
```bash
# After regenerating docs
git add content/en/docs/reference/config-api/*.md
git add content/en/docs/reference/kubernetes-api/**/*.md
git commit -m "Update reference docs for Kubernetes v1.29"
git push
```

---

### add-or-update-glossary-translation
**Trigger:** When a new glossary term is added or updated and needs translation  
**Command:** `/add-glossary-translation`

1. Translate the glossary term.
2. Add or update the relevant `.md` file under the appropriate language's glossary directory:
    - `content/zh-cn/docs/reference/glossary/*.md`
    - `content/vi/docs/reference/glossary/*.md`
3. Commit with a message referencing the glossary term and language.

**Example:**
```bash
# Add a Vietnamese glossary translation
cp upstream/glossary/new-term.md content/vi/docs/reference/glossary/new-term.md
git add content/vi/docs/reference/glossary/new-term.md
git commit -m "[vi] Add glossary term: new-term"
git push
```

## Testing Patterns

- Test files follow the pattern `*.test.*`
- The testing framework is **unknown** (not detected), but typical TypeScript test files might look like:
  ```typescript
  // example.test.ts
  import { myFunction } from './my-function';

  describe('myFunction', () => {
    it('should return true', () => {
      expect(myFunction()).toBe(true);
    });
  });
  ```
- Place test files alongside the code or in a dedicated test directory, using the `.test.ts` naming convention.

## Commands

| Command                    | Purpose                                                        |
|----------------------------|----------------------------------------------------------------|
| /sync-feature-gates-zh-cn  | Synchronize or add new feature gate docs in zh-cn reference    |
| /add-blog-zh-cn            | Add or update a blog post in the zh-cn localization            |
| /update-reference-en       | Bulk update English reference docs for new Kubernetes releases  |
| /add-glossary-translation  | Add or update glossary entries in localized documentation       |
```