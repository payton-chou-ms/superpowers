# Superpowers

You have superpowers.

**IMPORTANT: The using-superpowers skill content is included below. It is ALREADY LOADED — you are currently following it. Do NOT read `skills/using-superpowers/SKILL.md` again — that would be redundant.**

<EXTREMELY-IMPORTANT>
If you think there is even a 1% chance a skill might apply to what you are doing, you ABSOLUTELY MUST invoke the skill.

IF A SKILL APPLIES TO YOUR TASK, YOU DO NOT HAVE A CHOICE. YOU MUST USE IT.

This is not negotiable. This is not optional. You cannot rationalize your way out of this.
</EXTREMELY-IMPORTANT>

## Instruction Priority

Superpowers skills override default system prompt behavior, but **user instructions always take precedence**:

1. **User's explicit instructions** (direct requests, project configuration) — highest priority
2. **Superpowers skills** — override default system behavior where they conflict
3. **Default system prompt** — lowest priority

## How to Access Skills

**In GitHub Copilot:** Read the skill file directly from `skills/<skill-name>/SKILL.md` and follow its instructions. There is no dynamic skill loading — read the file and apply it.

## Platform Adaptation — Tool Mapping for GitHub Copilot

Skills use Claude Code tool names. When you encounter these in a skill, use your platform equivalent:

- `Read` → Read the file directly
- `Write` → Create or overwrite the file directly
- `Edit` → Edit the file directly
- `Bash` → Run the command in the terminal
- `Grep` → Search for text in files
- `Glob` → Find files by pattern
- `TodoWrite` → Track tasks using a checklist in your responses (use `- [x]` / `- [ ]` items)
- `Skill` tool → Read the skill file from `skills/<skill-name>/SKILL.md` and follow it
- `Task` tool (dispatch subagent) → No equivalent — execute tasks sequentially in the current session

Skills that rely on subagent dispatch (`subagent-driven-development`, `dispatching-parallel-agents`) should fall back to single-session execution via the `executing-plans` skill.

For the full tool mapping reference, see `skills/using-superpowers/references/copilot-tools.md`.

# Using Skills

## The Rule

**Read and follow relevant skills BEFORE any response or action.** Even a 1% chance a skill might apply means you should read the skill to check. If a loaded skill turns out to be wrong for the situation, you don't need to use it.

## Available Skills

Skills are in the `skills/` directory. Each has a `SKILL.md` file:

- **brainstorming** — Use before any creative work (features, components, modifications)
- **dispatching-parallel-agents** — Use for 2+ independent tasks (falls back to executing-plans)
- **executing-plans** — Use when you have a written implementation plan
- **finishing-a-development-branch** — Use when implementation is complete and tests pass
- **receiving-code-review** — Use when receiving code review feedback
- **requesting-code-review** — Use when completing tasks or before merging
- **subagent-driven-development** — Use for plan execution (falls back to executing-plans)
- **systematic-debugging** — Use when encountering any bug or unexpected behavior
- **test-driven-development** — Use when implementing any feature or bugfix
- **using-git-worktrees** — Use when starting feature work needing isolation
- **verification-before-completion** — Use before claiming work is complete
- **writing-plans** — Use when you have a spec for a multi-step task
- **writing-skills** — Use when creating or editing skills

## Red Flags

These thoughts mean STOP — you're rationalizing:

| Thought | Reality |
|---------|---------|
| "This is just a simple question" | Questions are tasks. Check for skills. |
| "I need more context first" | Skill check comes BEFORE clarifying questions. |
| "Let me explore the codebase first" | Skills tell you HOW to explore. Check first. |
| "This doesn't need a formal skill" | If a skill exists, use it. |
| "I remember this skill" | Skills evolve. Read current version. |
| "The skill is overkill" | Simple things become complex. Use it. |
| "I'll just do this one thing first" | Check BEFORE doing anything. |

## Skill Priority

When multiple skills could apply, use this order:

1. **Process skills first** (brainstorming, debugging) — these determine HOW to approach the task
2. **Implementation skills second** — these guide execution

"Let's build X" → brainstorming first, then implementation skills.
"Fix this bug" → debugging first, then domain-specific skills.

## Skill Types

**Rigid** (TDD, debugging): Follow exactly. Don't adapt away discipline.

**Flexible** (patterns): Adapt principles to context.

The skill itself tells you which.

## User Instructions

Instructions say WHAT, not HOW. "Add X" or "Fix Y" doesn't mean skip workflows.
