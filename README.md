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
git -c protocol.file.allow=always submodule add ../documentation-standards documentation/internal
git commit -m "Add shared documentation standards as submodule."
```

(`protocol.file.allow=always` is required for some Git versions when the submodule URL is a local `../` path.)

After you publish **documentation-standards** to a remote, update the submodule URL in the consuming repo (e.g. `git config submodule.documentation/internal.url https://github.com/org/documentation-standards.git`) so CI and other machines can clone without a sibling folder.

New clones of the consuming project:

```bash
git submodule update --init --recursive
```

Adjust the relative URL (`../documentation-standards`) if your layout differs, or use the HTTPS/Git remote URL of this repository.

### Copy

You may copy the Markdown files into your project when a submodule is not appropriate; treat this repository as the source of truth and sync changes manually.
