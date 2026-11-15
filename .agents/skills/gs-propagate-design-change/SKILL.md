---
name: gs-propagate-design-change
description: "Game studio workflow: Finds architecture decisions (ADRs) made stale by a changed GDD and walks through resolving each. Use when the user changed a number or rule in a GDD and asks which ADRs or architecture decisions are now out of date."
---

# propagate-design-change

Use this workflow only when it matches the user's game development request. Read the upstream reference at `upstream/.claude/skills/propagate-design-change/SKILL.md` from the project root, and only the references needed for this request. Resolve upstream `.claude/...` references as `upstream/.claude/...` and skill-relative references relative to that skill folder. Game project paths such as `design/`, `src/`, and `prototypes/` remain in the active project. Treat its Claude-specific syntax, agent routing, tool permissions, model selections, prompts, hook assumptions, and automatic commits as non-portable. Apply the intent using the current Codex tools, permissions, user instructions, and project context. Do not claim an automated hook, test, or specialist ran unless it actually did. Never invoke subagents unless authorized by the current session. If a referenced source file or script cannot work in this environment, explain the gap and use an appropriate available alternative.
