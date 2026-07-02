---
name: alldev
description: >
  Universal discipline for ALL software development, in any language, stack, or domain.
  ALWAYS trigger this skill when writing, generating, refactoring, or reviewing ANY code —
  applications, websites, APIs, scripts, CLIs, libraries, automations, bots, games,
  embedded systems, infrastructure — regardless of technology. Also trigger when planning
  or scaffolding a project, adding features, choosing libraries or frameworks, or fixing
  bugs. Even simple requests like "write a function", "create a script", or "add an
  endpoint" apply. If the task produces code, consult this skill first.
---

# AllDev Skill

Language-agnostic discipline for every development task: less code, zero dependencies,
clean and idiomatic output, Zero Trust security. This skill contains no code examples —
apply the principles to whatever language and stack are in use.

---

## 1. The best code is no code

Before writing anything, challenge the need to write it:

- **Question the feature.** Does it solve a real, current problem? If not, don't build it.
- **Platform first.** The language, runtime, standard library, and platform usually
  already solve the problem natively. Search there before writing custom code.
- **Simplest design that works today.** No abstractions for hypothetical futures,
  no options nobody asked for, no layers "for flexibility". YAGNI.
- **Delete before adding.** If a change lets you remove code, prefer it.

Checkpoint before coding: *"Can this be solved with less code — or none?"*
Answer it explicitly before proceeding.

## 2. Vanilla-first, zero dependencies

Default to zero external dependencies in every stack:

- Use only the native capabilities of the chosen language and platform.
- Reimplement small utilities instead of importing a library for them
  (rule of thumb: under ~200 lines of logic → write it yourself).
- A dependency is acceptable only when: (a) the problem is genuinely dangerous to
  hand-roll (payments, complex cryptography), (b) the user explicitly requested it,
  or (c) maintaining a native version costs more than the dependency's risk.
  State the justification whenever adding one.
- Prefer single-file or minimal-file architecture. No build steps or extra tooling
  unless strictly required.

## 3. Clean, readable, idiomatic, well-commented code

Code is read far more often than it is written. Optimize for the next reader:

- **Idiomatic first.** Follow the established conventions and best practices of the
  language in use — naming style, error-handling idiom, structure, formatting.
- **Respect the project.** In an existing codebase, its patterns override personal
  preference; new code must read as if written by the same author.
- **Names reveal intent.** Descriptive identifiers for variables, functions, and files.
  No cryptic abbreviations.
- **Small units, single responsibility.** Short functions that do one thing;
  early returns over deep nesting.
- **Comment the why, not the what.** Document decisions, business rules, trade-offs,
  and non-obvious constraints. Mark logical sections in long files for fast
  navigation. Never comment what the code already says.
- **No dead weight.** No dead code, no commented-out blocks, no duplication —
  but only extract shared code after a pattern repeats (rule of three);
  premature abstraction violates principle 1.

## 4. Zero Trust security

Assume every input, request, and boundary is hostile:

- **Never trust input.** Validate and sanitize everything from users, arguments,
  files, network, third parties, and even the database — at the boundary where
  it enters.
- **Escape at output.** Context-aware encoding for wherever the data lands
  (markup, queries, commands, file paths). Use the stack's safe output primitives;
  never build queries or commands by string concatenation.
- **Deny by default.** Allowlists over blocklists; least privilege for operations,
  tokens, credentials, and file permissions.
- **Secure defaults.** Encrypted transport and storage where applicable; hardened
  session and state handling; abuse and rate limiting on exposed surfaces; modern
  password hashing; constant-time comparison for secrets; no secrets in code,
  logs, or version control.
- **Fail closed.** Errors never expose internals or grant access.

If a dedicated security skill (e.g. SkillSec) is available, defer to it for depth.

---

## Mandatory review passes

Never deliver a first draft. Before finishing, run:

1. **Simplification pass** — reread everything asking "what can be removed?"
   Cut dead code, redundant abstractions, unused options, premature generality.
2. **Readability pass** — check naming, idioms, structure, consistency, and
   comments as if reading the code for the first time.
3. **Security pass** — trace every external value from entry to output. Check
   injection of every kind, authn/authz on every entry point, secrets handling,
   error leakage.
4. **Adversarial pass** — re-review assuming the previous pass missed something.
   Attack your own code: "how would I exploit this?" Fix, then re-check the fix.

Repeat passes 3–4 until a full pass finds nothing. Only then deliver.

## Quick decisions

| Situation | Do |
|---|---|
| "We might need X later" | Don't build X |
| Library for < ~200 lines of logic | Write it natively |
| The platform already does it | Use the platform |
| Any external input touched | Validate → sanitize → escape |
| Same code repeated twice | Wait for the third before abstracting |
| Code "done" on the first try | It isn't — run the 4 passes |
