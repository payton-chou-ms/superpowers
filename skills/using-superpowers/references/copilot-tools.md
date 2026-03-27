# GitHub Copilot Tool Mapping

Skills use Claude Code tool names. When you encounter these in a skill, use your platform equivalent:

| Skill references | GitHub Copilot equivalent |
|-----------------|--------------------------|
| `Read` (file reading) | Read the file directly (use workspace file access) |
| `Write` (file creation) | Create or overwrite the file directly |
| `Edit` (file editing) | Edit the file directly |
| `Bash` (run commands) | Run the command in the terminal |
| `Grep` (search file content) | Search for text in files |
| `Glob` (search files by name) | Find files by pattern |
| `TodoWrite` (task tracking) | Track tasks in your response — list items with checkboxes and update status as you progress |
| `Skill` tool (invoke a skill) | Read the skill file from `skills/<skill-name>/SKILL.md` and follow its instructions |
| `Task` tool (dispatch subagent) | No equivalent — execute tasks sequentially in the current session |

## No subagent support

GitHub Copilot does not support dispatching subagents. Skills that rely on subagent dispatch (`subagent-driven-development`, `dispatching-parallel-agents`) should fall back to single-session execution via `executing-plans`.

## Skill loading

GitHub Copilot does not have a native `Skill` tool. When a skill tells you to invoke another skill:

1. Read the skill file at `skills/<skill-name>/SKILL.md`
2. Follow its instructions directly

## Task tracking

When a skill calls for `TodoWrite`, maintain a visible checklist in your responses:

```markdown
- [x] Completed item
- [ ] Pending item
- [ ] Next item
```

Update the checklist as you complete each item.
