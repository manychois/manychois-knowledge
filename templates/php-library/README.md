# PHP library — project template files

Copy these files into a new repository root and adjust placeholders.

| File | Purpose |
|------|---------|
| [`composer.json`](composer.json) | Package metadata, autoload, dev tools, Composer scripts. |
| [`phpcs.xml`](phpcs.xml) | PHPCS: PSR-12 + PEAR docblocks + Slevomat rules (aligned with [`php-coding-standard.md`](../../php-coding-standard.md)). |
| [`phpstan.dist.neon`](phpstan.dist.neon) | PHPStan `max` level on `src/` and `tests/`. |
| [`phpunit.xml`](phpunit.xml) | PHPUnit testsuite + coverage for `src/`. |

## `composer.json` placeholders

Replace at least:

- **`name`**: e.g. `manychois/your-package`
- **`description`**, **`license`**, **`authors`**
- **`autoload` / `autoload-dev` PSR-4** prefixes and paths (e.g. `YourOrg\\YourPackage\\` → `src/`, `YourOrg\\YourPackage\\Tests\\` → `tests/`)
- **`require`**: add runtime dependencies (`ext-*`, libraries)

Then:

```bash
composer install
composer test
composer analyse   # if you add an analyse script aliasing phpstan
```

PHPCS references `vendor/slevomat/coding-standard`; run `composer install` first so that path exists.

If you analyse only production code, remove `tests` from `phpstan.dist.neon` `paths`. If you do not lint tests yet, remove the `./tests` `<file>` line from `phpcs.xml`.
