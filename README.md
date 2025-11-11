# Hooked Rules for TSI

This rule-set for [hooked](https://github.com/conmob-devsecops/hooked)
contains a curated set of hooks specifically for TSI.

## 📦 Installation

```bash
hooked install https://github.com/conmob-devsecops/hooked-ruleset-tsi.git
```

⚠️ Beside `hooked` you need to have [Gitleaks](https://github.com/gitleaks/gitleaks)
installed and available in your PATH for this rule-set to work. Pre-build binaries
of gitleaks are available on the [releases page](https://github.com/gitleaks/gitleaks/releases).

## Usage

This rule-set contains an opinionated gitleaks configuration, that may affect
your ability to commit. Therefore,

### ✅ Allowed

Secrets in the following folders and files are allowed. Here you can place contributions
without risking false positives from gitleaks scans.

- `docs/*`
- `contrib/*`
- `examples/*`, `tests/*`, `fixtures/*`, `samples/*`
- `README.md`

### ⛔️ Denied

- Common files in software development, that contain secrets (e.g., `.env`, `.env.local`)
- Files, that should never be part of a commit (e.g., `.DS_Store`, `Thumbs.db`)
- Employee ID (so called "A-Kennung")
- Commit author email addresses other than `t-systems.com` or `telekom.de`
  (including externals)
- **Secrets!** 🔥

### 📌 False Positive Handling

False positives might occur when gitleaks erroneously detects a secret as a
potential leak. To ignore a false positive using inline comments, follow these
steps:

- Identify the specific line of code that is generating the false positive.
- Place an inline comment on the same line as the false positive. The comment
  must start with `gitleaks:allow`
- Add a reason for the ignore, for example, `gitleaks:allow: this is a test
secret`
- Commit the changes and push them to the repository.
- Gitleaks will now ignore the false positive and not flag it as a potential
  leak.

## Available Hooks

| Hook                         | Description                                                 |
| ---------------------------- | ----------------------------------------------------------- |
| `gitleaks-staged`            | Runs local gitleaks on staged changes                       |
| `check-git-user-email`       | Disallows git author emails other than from allowed domains |
| `check-prohibited-filenames` | Disallow certain filenames, similar to .gitignore patterns. |

## Issues

If you face any issues when using this rule-set in your daily job, we'd like to
hear from! You may start an issue in this repository or write us an email at
[devsecops@t-systems.com](mailto:devsecops@t-systems.com).
