# manychois-knowledge

Shared knowledge base: reusable documentation and conventions for **manychois** projects (Diátaxis reference, PHP coding style, and room to grow).

| File | Purpose |
|------|---------|
| [`diataxis-framework-reference.md`](diataxis-framework-reference.md) | Diátaxis framework for technical writing (tutorials, how-to, reference, explanation). |
| [`php-coding-standard.md`](php-coding-standard.md) | PHP style conventions (docblocks, structure, PHPUnit naming, etc.). |

## Project templates

| Path | Purpose |
|------|---------|
| [`templates/php-library/`](templates/php-library/) | Starting **composer.json**, **phpcs.xml**, **phpstan.dist.neon**, and **phpunit.xml** for a PHP library (placeholders for vendor namespace; PHPCS rules match the coding standard doc). |

## Using in a project

### Git submodule (recommended)

From your project repository root (sibling clone layout: `projects/my-app` and `projects/manychois-knowledge`):

```bash
git -c protocol.file.allow=always submodule add ../manychois-knowledge documentation/internal
git commit -m "Add manychois-knowledge as submodule."
```

(`protocol.file.allow=always` is required for some Git versions when the submodule URL is a local `../` path.)

After you publish **manychois-knowledge** to a remote, update the submodule URL in the consuming repo (e.g. `git config submodule.documentation/internal.url https://github.com/manychois/manychois-knowledge.git`) so CI and other machines can clone without a sibling folder.

New clones of the consuming project:

```bash
git submodule update --init --recursive
```

Adjust the relative URL (`../manychois-knowledge`) if your layout differs, or use the HTTPS/Git remote URL of this repository.

### Copy

You may copy the Markdown files into your project when a submodule is not appropriate; treat this repository as the source of truth and sync changes manually.
