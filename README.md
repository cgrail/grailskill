# grailskill

A Claude Code plugin with the rules every project shares.

| Skill | What it does |
| --- | --- |
| `rules` | The house rules: files under 300 lines, 90%+ test coverage, simple words, no brand names, who tests what, changelog and commits. |
| `todo` | Works items off `todo.md`, one commit per item. Run it with `/grailskill:todo`. |

## Install

```
/plugin marketplace add cgrail/grailskill
/plugin install grailskill@grailskill
```

A project's own `CLAUDE.md` wins where it says otherwise, so it only needs what is special about that project.
