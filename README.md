# Renovate Config

Opinionated [Renovate](https://docs.renovatebot.com/) configuration for keeping dependencies up to date with minimal noise.

## What it does

* Extends Renovate's recommended configuration
* Enables the Dependency Dashboard
* Uses semantic commits with `chore` as the commit type
* Runs during the final weekend window of each month
* Disables patch updates
* Delays minor and major updates by 7 days
* Requires strict internal checks for minor and major updates

## Usage

Add the following to `.github/renovate.json` or `renovate.json`:

```json
{
  "extends": ["github>favorodera/renovate-config"]
}
```

## Update policy

* **Patch updates:** Disabled
* **Minor updates:** Allowed after a 7-day release age
* **Major updates:** Allowed after a 7-day release age
* **Internal checks:** Strict for minor and major updates
* **Schedule:** Final weekend window of every month

This configuration is designed to reduce dependency-update noise while still keeping dependencies reasonably up to date.
