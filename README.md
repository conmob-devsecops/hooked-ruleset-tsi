# hooked-ruleset-tsi

This repository containts configurations to be used with the [hooked](https://github.com/conmob-devsecops/hooked) tool.

## Installation

Point `hooked` to this repository, for example:

```bash
hooked install --rules git@github.com:conmob-devsecops/hooked-ruleset-tsi.git
```

## Hooks

### check-git-user-email

Only allow commits, if git user email is using a domain included in the allowed set of domains.

### trailing-whitespace

Trims trailing whitespace, see [trailing-whitespace](https://github.com/pre-commit/pre-commit-hooks?tab=readme-ov-file#trailing-whitespace)

### gitleaks-staged

Runs local gitleaks scan on staged changes only, see [gitleaks](https://github.com/gitleaks/gitleaks) for more information
and how to install. Pre-build binaries are available on the [releases page](https://github.com/gitleaks/gitleaks/releases).

**Note:** You need to have `gitleaks` installed and available in your PATH for this hook to work.
