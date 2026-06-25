# Renovate Config

Opinionated Renovate bot configuration.

## What it does

- Extends recommended config with dependency dashboard and semantic commits
- Runs Monday 5am
- Disables patch updates
- Minor/major updates wait 7 days with strict checks
- Lock file maintenance enabled

## How to use

Add to `.github/renovate.json` or `renovate.json`:

```json
{
  "extends": ["github>favorodera/renovate-config"]
}
```
