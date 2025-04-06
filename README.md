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
      # must add types to match files you want to format
      types:
        - javascript
        - ts
        - yaml
        - toml
```
