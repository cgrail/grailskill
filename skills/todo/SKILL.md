---
name: todo
description: Work items off todo.md, one at a time, with one commit per finished item. Use when asked to work on the todos, to do the next todo, or when handed a todo item by name.
allowed-tools: Read, Edit, Write, Grep, Glob, Bash
---

## The list

!`cat todo.md 2>/dev/null || echo "No todo.md at the repo root."`

`todo.md` at the repo root is the backlog. `[ ]` is open and `[x]` is done. Done items stay in the file as a record.

Arguments, if any, name which items to take (a number, a keyword, "all"). With no arguments, take the **topmost `[ ]` item** and keep going down the list. If a later item is a prerequisite for an earlier one, do it first and say so in its commit body.

## One item = one commit

For each item, in order:

1. **Read the item as a bug report, not a spec.** Most entries are one line of the user's shorthand. Find the actual code before deciding what the fix is: the symptom is usually a small piece of a shared code path.
2. **Locate it.** The project's CLAUDE.md maps the folders. Follow the change through every layer and platform it touches. Where two builds mirror each other, both change in the same commit.
3. **Implement.** Follow [develop-like-christian-grail](../develop-like-christian-grail/SKILL.md) and every constraint in CLAUDE.md that the change touches.
4. **Verify.** Run every headless check CLAUDE.md names. A new or changed behavior gets one test that fails without it.
5. **Changelog and docs**, as that skill says. A changed invariant, or a rule a future edit could break, goes into the matching section of CLAUDE.md. A bug fix that changes no rule needs none of them.
6. **Tick the item** in `todo.md`: `[ ]` → `[x]`. A follow-up the user should decide on becomes a new `[ ]` line.
7. **Commit everything for the item together:** code, tests, `todo.md`, the changelog and docs. Push when CLAUDE.md says to. If the push is rejected because the branch moved, rebase, run the checks again and push as a normal push.

## Reporting

After each commit, tell the user in two or three lines:

- what the item turned out to be
- what changed
- **what to check by hand**: the device and browser checks you left to them

Then start the next item without asking. Stop only when the list is empty, when an item needs a decision only the user can make, or when you run out of room.
