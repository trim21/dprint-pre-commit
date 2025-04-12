# dprint pre-commit mirror

Mirror of `dprint` package for pre-commit.

For pre-commit: see https://github.com/pre-commit/pre-commit

For dprint: see [https://github.com/dprint/dprint](https://github.com/dprint/dprint)

### Using dprint with pre-commit

Add this to your `.pre-commit-config.yaml`:

```yaml
- repo: https://github.com/trim21/dprint-pre-commit
  rev: "" # Use the sha / tag you want to point at
  hooks:
    - id: dprint
      # must add types_or to match files you want to format
      types_or:
        - javascript
        - ts
        - yaml
        - toml
```

## Gotcha!

dprint doesn't take args as file path, but actually as glob pattern.

So if your file path contains any `[` or `]`, it will nevery get formatted

The solution would be letting dprint format all files:

```yaml
- repo: https://github.com/trim21/dprint-pre-commit
  rev: "" # Use the sha / tag you want to point at
  hooks:
    - id: dprint
      pass_filenames: false
      always_run: true
```

If your project contains git submodules, don't forget to exclude then in `dprint.json`
