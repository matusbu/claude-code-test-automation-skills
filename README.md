# claude-code-test-automation-skills

Reusable Claude Code skills for test automation workflows.

---

## Available skills

| Skill | What it does | Invoke with |
|---|---|---|
| `verify-test-coverage` | Analyzes your code changes and checks them against your defined test strategy. Reports what's covered, what's missing, and what tests to write. | `/verify-test-coverage [scope]` |

---

## Getting started

- Copy the [`.claude/`](.claude/) folder into your project root
- Make sure you have a `TEST_STRATEGY.md` in your project root — use the [template](TEST_STRATEGY_TEMPLATE.md) or see a [real example](TEST_STRATEGY_EXAMPLE.md)
- Run the skill, e.g. `/verify-test-coverage branch`

---

More skills coming.
