# Copilot Instructions — README

**File:** `copilot-instructions.md`
**Maintained by:** Upadrasta Harsha Vardhan

This document explains, in plain language, what `copilot-instructions.md`
is, what it does, and why it's useful.

---

## What is it?

`copilot-instructions.md` is a **custom instructions file** for GitHub
Copilot. It's just a plain Markdown file — no plugin, no extension, no
third-party install. You place it at:

```
.github/copilot-instructions.md
```

in any repository, and GitHub Copilot automatically reads it and applies
its rules every time it generates code, answers a chat question, or
reviews a change **in that repo**.

Think of it as a written brief you hand to a new senior developer on day
one: "here's how we like to write code on this team."

---

## Why it exists

By default, AI coding assistants tend to:

- Over-engineer simple problems (adding config options, abstractions,
  or libraries nobody asked for)
- Write more code than the task actually needs
- Sometimes make big/risky changes without checking in first

This file fixes that by giving Copilot a consistent set of ground rules
to follow automatically, every single time — so you don't have to repeat
yourself in every chat.

---

## How it works

1. You drop the file into `.github/copilot-instructions.md` in your repo.
2. Copilot reads it automatically in the background.
3. Every suggestion, chat answer, or code edit Copilot gives you in that
   repo now follows the rules in the file — no extra setup, no toggling
   anything on.

It works the same way across **any language or framework** — Python,
JavaScript, Java, Go, etc. — because the rules are about *how to think*,
not about any specific tech stack.

---

## Features

| Section | What it does |
|---|---|
| **1. Before writing new code** | Makes Copilot check — in order — whether the code is actually needed, already exists, or can be solved with a standard library/framework feature before writing anything new. |
| **2. Design & abstraction** | Stops Copilot from adding unnecessary complexity (interfaces, factories, config layers) for problems that don't need them yet. |
| **3. Correctness & safety** | Copilot will never strip out validation, error handling, or tests just to make code shorter. |
| **4. Security-specific checks** | Enforces safe handling of user input, no hardcoded secrets, no SQL injection risk, proper output escaping. |
| **5. Performance** | Avoids premature optimization, but applies real fixes (no N+1 queries, no unbounded loops) when performance actually matters. |
| **6. Working within an existing codebase** | Keeps Copilot's style consistent with your existing code and stops it from refactoring unrelated files. |
| **7. When unsure** | Copilot states its assumptions out loud instead of silently guessing. |
| **8. Approval before big changes** | Copilot proposes a short plan and **waits for your go-ahead** before doing anything complex, risky, or hard to undo (new architecture, schema changes, auth/payment logic, destructive commands like `rm -rf` or force-push). |

---

## Advantages of using this file

- ✅ **Safer by default** — third-party plugins can change, get
  abandoned, or (in theory) include hidden instructions. This file is
  100% yours, plain text, and fully auditable by you or your company's
  IT/security team.
- ✅ **No installation needed** — works the moment it's in the repo; no
  extension marketplace, no permissions, no external dependency.
- ✅ **Company/license-safe** — since it's just a Markdown file you
  wrote, it doesn't raise the same "is this third-party tool approved"
  question that installing an external plugin does.
- ✅ **Consistent AI behavior across your whole team** — anyone using
  Copilot on the repo gets the same ground rules automatically, so
  suggestions feel consistent no matter who's coding.
- ✅ **Less cleanup work** — fewer unnecessary abstractions and less
  bloated code to review and maintain later.
- ✅ **Fewer surprises** — Copilot checks in with you before big or
  risky changes instead of just doing them.
- ✅ **Works everywhere** — one file, reusable across any project
  regardless of language or framework.
- ✅ **Fully editable** — it's your file; tweak, add, or remove rules
  any time to match your team's preferences.

---

## How to use it

1. Copy `copilot-instructions.md` into your repository at:
   ```
   .github/copilot-instructions.md
   ```
2. Commit it like any normal file.
3. That's it — Copilot will pick it up automatically for that repo from
   then on.

Optional: edit any section to match your team's specific standards
(e.g. stricter security rules, a preferred testing framework, naming
conventions).
