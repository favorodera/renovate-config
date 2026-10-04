# Renovate Config

Opinionated [Renovate](https://docs.renovatebot.com/) configuration for keeping dependencies up to date with minimal noise, built around CI-gated automerge.

## What it does

* Extends Renovate's recommended configuration
* Enables the Dependency Dashboard
* Uses semantic commits with `chore` as the commit type
* Runs patch/minor updates weekly, grouped into a single PR
* Runs major updates monthly, left for manual review
* Limits concurrent and hourly PR volume across repos

## Usage

Add the following to `.github/renovate.json` or `renovate.json`:

```json
{
  "extends": ["github>favorodera/renovate-config"]
}
```

Requires your repo's branch protection to require your CI checks (lint, build, typecheck, test, and pkg.pr for libraries) before merge, and "Allow auto-merge" enabled in repo settings — this is what makes automerge safe, not Renovate itself.

## Update policy

| Update type | Release age delay | Schedule | Automerge |
|---|---|---|---|
| Patch | 3 days | Weekly (Monday, before 4am UTC) | Yes |
| Minor | 3 days | Weekly (Monday, before 4am UTC) | Yes |
| Major | 7 days | Monthly (1st, before 4am UTC) | No — manual review |

* **Internal checks:** Strict for all updates
* **Grouping:** All non-major updates are grouped into a single weekly PR to reduce review overhead
* **Concurrency:** Max 8 open PRs and 3 new PRs per hour, to avoid flooding multiple repos at once

This configuration is designed to spread dependency updates out over time, lean on CI as the real safety gate, and reserve manual review for major version bumps only.