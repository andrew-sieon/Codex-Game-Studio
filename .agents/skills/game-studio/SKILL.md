---
name: game-studio
description: Design, prototype, test, and iteratively improve games in Codex. Use for game brainstorming, playable prototypes, game design, game development and playtest-driven revisions.
---

# Game Studio for Codex

Turn the user's idea into a game they can actually play and revise. This is a Codex adaptation of Claude Code Game Studios, not an emulation of Claude Code. The user controls scope and creative choices. Follow higher-priority instructions and the user's explicit requests.

## Route by intent

- **Brainstorm:** for an open or rough idea, offer 2–3 meaningfully different concise concepts and ask the user to pick, combine, or propose another. When they already chose an idea, continue without repeating the choice. See `upstream/.claude/skills/brainstorm/SKILL.md` for source context, not Claude-specific commands.
- **Prototype/build:** identify the core loop, controls, win/loss, art direction and first playable slice. Ask only when a missing decision materially changes the result; otherwise make clear, reasonable assumptions and build. If a reference image exists, inspect it before deciding the visual approach, and list the important visual traits in the brief. Write a short brief to the game folder, preserving the user's words and separating assumptions. Build a complete playable slice, not just a mockup. Put reusable tuning values in a separate config where appropriate.
- **Improve an existing game:** inspect and run the existing game if possible; preserve what the user wants retained, implement the requested change, verify it, and explain what changed.
- **Other game workflows:** identify the closest folder under `upstream/.claude/skills/`; read its SKILL.md and only relevant references as domain guidance. Apply them using Codex tools and current instructions. Upstream scripts and references may assume Claude environment variables, hooks, or project layout; inspect preconditions before invoking. Do not claim an upstream workflow, script, hook, or specialist ran if it did not.

## Visual quality and assets

Match requested visual style and reference through character proportions, silhouettes, palette, backgrounds, composition and animation. Do not substitute simplistic geometric placeholders or emoji for finished character art without telling the user. If image generation is available and appropriate, use it to create original consistent assets. Otherwise create or source suitable assets within permissions, or label visual limitations. A screenshot reference is visual guidance, not evidence of its source assets, toolchain, mechanics, or animation. Do not promise pixel-identical replication or copy protected assets.

## Build and verify

- Keep the project self-contained when practical; provide straightforward launch instructions and avoid external runtime dependencies for a standalone prototype when possible.
- Implement a coherent loop, responsive input, visible feedback, restart, and accessible controls. Include a meaningful end condition when appropriate. Separate artwork, game logic and tuning values when that helps iteration.
- Run relevant checks: syntax/build, startup and input, and visual inspection where the environment permits. Check collision, scoring, loss/win and restart for action games. Fix observed errors before delivery. Never bypass browser or system security restrictions to test.
- Distinguish observed results, automated checks, and untested aspects. Never claim human playtesting occurred when it did not. Ask for player feedback when useful.
- Preserve existing files and work; do not overwrite a separate game without the user's instruction.

## Codex operating model

Use Codex tools available in the current session. Claude `Agent`, `AskUserQuestion`, slash-command names, frontmatter tool allowlists, hooks, model names, and permissions do not automatically translate. Follow the current session's delegation rules. Original hooks do not run automatically. Apply useful checks explicitly and report any that could not run. Never imply 49 agents are running.
