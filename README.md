# Shared documentation standards

Canonical copies of reusable documentation used across PHP and other projects:

| File | Purpose |
|------|---------|
| [`diataxis-framework-reference.md`](diataxis-framework-reference.md) | Diátaxis framework for technical writing (tutorials, how-to, reference, explanation). |
| [`php-coding-standard.md`](php-coding-standard.md) | PHP style conventions (docblocks, structure, PHPUnit naming, etc.). |

## Using in a project

### Git submodule (recommended)

From your project repository root (sibling clone layout: `projects/my-app` and `projects/documentation-standards`):

```bash
git submodule add ../documentation-standards documentation/internal
git commit -m "Add shared documentation standards as submodule."
```

New clones:

```bash
git submodule update --init --recursive
```

Adjust the relative URL (`../documentation-standards`) if your layout differs, or use an absolute repository URL after publishing.

### Copy

You may copy the Markdown files into your project when a submodule is not appropriate; treat this repository as the source of truth and sync changes manually.
