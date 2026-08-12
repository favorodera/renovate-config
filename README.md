# Renovate Config

Opinionated [Renovate](https://docs.renovatebot.com/) configuration for keeping dependencies up to date with minimal noise.

## What it does

- Extends Renovate's recommended configuration
- Enables the Dependency Dashboard
- Uses semantic commits with `chore` as the commit type
- Runs every weekend
- Disables patch updates
- Delays minor and major updates by 7 days
- Requires strict internal checks for minor and major updates
- Enables lock file maintenance

## Usage

Add the following to `.github/renovate.json` or `renovate.json`:

```json
{
  "extends": ["github>favorodera/renovate-config"]
}
