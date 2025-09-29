# hooked-ruleset-tsi

This repository containts configurations to be used with the [hooked](https://github.com/conmob-devsecops/hooked) tool.

## Installation

Point `hooked` to this repository, for example:

```bash
hooked install git@github.com:conmob-devsecops/hooked-ruleset-tsi.git
```

## Hooks

### check-git-user-email

Only allow commits, if git user email is using a domain included in the allowed set of domains.

### check-prohibited-filenames

Disallow certain filenames, similar to .gitignore patterns.

### trailing-whitespace

Trims trailing whitespace, see [trailing-whitespace](https://github.com/pre-commit/pre-commit-hooks?tab=readme-ov-file#trailing-whitespace)

### gitleaks-staged

Runs local gitleaks scan on staged changes only, see [gitleaks](https://github.com/gitleaks/gitleaks) for more information
and how to install. Pre-build binaries are available on the [releases page](https://github.com/gitleaks/gitleaks/releases).

**Note:** You need to have `gitleaks` installed and available in your PATH for this hook to work.

#### Gitleaks configuration

The gitleaks configuration file `.gitleaks.toml` is included in this repository. It extends the default gitleaks ruleset
with some additional rules and exclusions.

Excluded paths:

- /docs/
- /contrib/
- /examples/

Here you can store documentation, example code and community contributions without risking false positives from
gitleaks scans.

Also excluded are auto-generated files of commonly used package managers for various programming languages.
