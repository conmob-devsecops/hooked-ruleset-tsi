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
