---
name: develop-like-christian-grail
description: How Christian Grail develops in every project (file size, tests, wording, who tests what, changelog, commits). Use before writing or changing code, tests, docs or UI text.
---

The project's own CLAUDE.md wins where it says otherwise.

## Code

- **Files stay under 300 lines.** When a change pushes one past that, split it along a feature seam as part of the same change.
- **Logic lives where the tests reach it.** Views and glue code stay thin and only call it.
- **Match the surrounding code.** Comments say only the why.
- **Saved data keeps loading.** Stored keys keep their names and meaning.

## Tests

- **Every logic file has 90%+ line coverage**, measured with the project's coverage tool.
- **One behavior, one test.** A new or changed behavior adds or changes one test that fails without it.

## Words

In code, UI text and docs:

- **Simple words everybody understands:** `name`, not `callsign`.
- **Generic words in place of brand names:** describe the thing ("a classic racing game"), whoever makes it.

## Who tests what

- **You run the headless checks:** syntax and type checks, unit tests, a compile. They are all green before a commit.
- **The developer runs every test on a device or in a browser**, and judges how it looks, sounds and feels. Leave the browser, the simulator and the device to them, and end each change with the list of checks for them to run by hand.

## Finishing a change

- **Changelog:** a change a user would notice gets its entry in the project's `CHANGELOG.md` in the same commit. Say what the product does now, not what the diff did.
- **README:** a new or changed feature, control or setting updates it in the same commit.
- **Commit message:** an imperative subject of about 60 characters with no scope prefix. Add a body only when the why isn't obvious.
- **Push** only when the project's CLAUDE.md says to, and only with every check green.
