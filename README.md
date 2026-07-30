# Zest skills

Agent skills for [Zest](https://github.com/SEORY0/zest) — a local-first data and security
workbench. Encode, decode, hash, encrypt, decompress and analyse data without anything leaving
the machine.

## Install

```bash
npx skills add SEORY0/zest-skill
```

To install just one:

```bash
npx skills add SEORY0/zest-skill --skill zest
npx skills add SEORY0/zest-skill --skill zest-triage
```

## What is in here

| Skill | For |
| --- | --- |
| [`zest`](skills/zest/SKILL.md) | Encode, decode, hash, encrypt, decrypt and inspect data with the local `zest` CLI. |
| [`zest-triage`](skills/zest-triage/SKILL.md) | Triage an unknown or suspicious artefact — a file, a captured blob, a log, a phishing mail, an obfuscated string — using the local `zest` CLI. |

## The CLI

Both skills drive the `zest` command. Install it once — it needs Node 20 or newer:

```bash
git clone https://github.com/SEORY0/zest.git
cd zest && npm install && npm run build && npm link -w @zest/cli
```

```console
$ echo 'SGVsbG8sIHdvcmxkIQ==' | zest from-base64
Hello, world!

$ echo 'U0dWc2JHOHNJSGR2Y214a0lRPT0=' | zest magic:depth=2
 1. from-base64 → from-base64
    score 35  (fully printable ASCII, entropy fell 0.74 bits)
    Hello, world!
```

There is a browser version at <https://seory0.github.io/zest/> for when a command line is not
available.

## Note

This repository is generated. `skills/` is mirrored from the
[main repository](https://github.com/SEORY0/zest), where `references/operations.md` is built
from the operation registry itself — so the catalogue an agent reads always matches the code.
Open issues and pull requests there.

MIT licensed.
