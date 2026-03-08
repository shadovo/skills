# Skills — AI Agent Skill Files

A curated collection of reusable **SKILL.md** files for AI coding agents (e.g. GitHub Copilot, Cursor, Claude, etc.). Each skill teaches an agent a focused, repeatable behavior that you can drop into any project.

---

## Why this repo exists

AI agents are most effective when they have clear, concise instructions for specific tasks. Instead of re-explaining the same patterns in every project, you can reference a skill file from this collection and get consistent, high-quality results instantly.

Goals:
- **Reusability** – define a behavior once, use it across many projects.
- **Consistency** – every engineer on your team gets the same agent behavior.
- **Discoverability** – browse skills by name and pick only what you need.

---

## Repository structure

```
skills/
├── README.md                  ← you are here
├── harsh-code-review/
│   └── SKILL.md               ← skill definition
├── another-skill-name/
│   └── SKILL.md
└── ...
```

Each top-level folder is named after the skill it contains and holds exactly one `SKILL.md` file with the full skill definition.

---

## How to use a skill

1. **Browse** the folders in this repo and find a skill that fits your need.
2. **Copy** the contents of the relevant `SKILL.md` into your project — for example into `.github/copilot-instructions.md`, a Cursor rules file, or directly into a prompt.
3. **Invoke** the skill in your agent session by referencing its instructions or simply by having the file present in your workspace context.

### Example — adding a skill to a GitHub Copilot project

```bash
# from the root of your project
# replace 'main' with a specific tag or commit SHA for reproducible results
mkdir -p .github
curl -fsSL https://raw.githubusercontent.com/shadovo/skills/main/harsh-code-review/SKILL.md \
  > /tmp/skill.md

# append to existing instructions with a blank-line separator, then clean up
echo "" >> .github/copilot-instructions.md
cat /tmp/skill.md >> .github/copilot-instructions.md
```

---

## Skill format

Every `SKILL.md` follows a consistent structure so that agents can parse and apply it reliably:

```markdown
# <Skill Name>

## Purpose
One-sentence description of what this skill makes the agent do.

## Instructions
Step-by-step or rule-based instructions the agent must follow.

## Examples (optional)
Concrete before/after examples that illustrate the skill in action.
```

---

## Contributing a new skill

1. Create a new folder with a descriptive, kebab-case name (e.g. `my-new-skill/`).
2. Add a `SKILL.md` file inside it following the format above.
3. Open a pull request — keep one skill per PR for easier review.

---

## Available skills

| Skill | Description |
|-------|-------------|
| [harsh-code-review](./harsh-code-review/SKILL.md) | Instructs the agent to perform a thorough, uncompromising code review that prioritizes correctness, readability, and maintainability. |

---

## License

MIT
