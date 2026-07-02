# AllDev Skill 0.1

**Minimal code · Zero dependencies · Zero Trust**

A lean, language-agnostic Skill that disciplines AI coding assistants on every development task. It activates whenever code is written, generated, refactored, or reviewed — in any language, stack, or domain — and enforces four ordered principles plus mandatory review passes before anything is delivered.

Designed to be as small as possible so it stays cheap in tokens while active on every task.

English | [Português](README.br.md) | [Español](README.es.md)

## Why

AI coding assistants tend to over-engineer, reach for dependencies by default, produce generic non-idiomatic code, and treat security as an afterthought. AllDev Skill inverts those defaults:

1. **The best code is no code** — every feature is challenged before it's written. Platform-native solutions come first; YAGNI applies always; deleting code beats adding it.
2. **Vanilla-first, zero dependencies** — only the native capabilities of the chosen language and platform. Utilities under ~200 lines are written by hand. Every dependency requires an explicit justification.
3. **Clean, readable, idiomatic, well-commented code** — the language's conventions and the project's existing patterns come first; intent-revealing names, small single-responsibility units, and comments that explain the *why*, never the *what*.
4. **Zero Trust security** — no input is trusted, output is escaped by context, access is denied by default, defaults are secure, and failures close instead of open.

On top of that, no first draft ships. Four review passes are mandatory: **simplification**, **readability**, **security**, and an **adversarial pass** where the assistant attacks its own code — repeated until a full pass finds nothing.

## What it is not

- Not a stack guide. It contains **no code examples** and never prescribes a language, framework, or tool.
- Not a replacement for a dedicated security skill.

## Installation

The skill is a single folder with a single file:

```
alldev/
└── SKILL.md
```

**Claude Code** — personal (all projects):

```bash
git clone https://github.com/gmasson/alldev.git ~/.claude/skills/alldev
```

Or per project:

```bash
git clone https://github.com/gmasson/alldev.git .claude/skills/alldev
```

**Other tools** — any assistant supporting the Agent Skills standard (Claude.ai, Cursor, Windsurf, GitHub Copilot, and others): copy the `alldev/` folder into the tool's skills directory. For tools without skill support, paste the contents of `SKILL.md` into the assistant's rules or custom instructions file.

## When it triggers

Any task that produces code: applications, websites, APIs, scripts, CLIs, libraries, automations, bots, games, embedded systems, infrastructure — including small requests like "write a function" or "create a script", and also when planning projects, adding features, choosing libraries, or fixing bugs.

## License

[MIT](LICENSE)

## Author

Gabriel Masson — [github.com/gmasson](https://github.com/gmasson)
