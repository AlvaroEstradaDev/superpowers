---
name: using-superpowers
description: Use when starting any conversation - establishes how to find and use skills, requiring Skill tool invocation before ANY response including clarifying questions
---

<SUBAGENT-STOP>
If you were dispatched as a subagent to execute a specific task, skip this skill.
</SUBAGENT-STOP>

<EXTREMELY-IMPORTANT>
If you think there is even a 1% chance a skill might apply to what you are doing, you ABSOLUTELY MUST invoke the skill.

IF A SKILL APPLIES TO YOUR TASK, YOU DO NOT HAVE A CHOICE. YOU MUST USE IT.

This is not negotiable. This is not optional. You cannot rationalize your way out of this.
</EXTREMELY-IMPORTANT>

## Instruction Priority

1. **User instructions** (CLAUDE.md, GEMINI.md, AGENTS.md, direct requests) — highest priority
2. **Superpowers skills** — override default system prompt
3. **Default system prompt** — lowest priority

If CLAUDE.md says "don't use TDD" and a skill says "always use TDD," follow the user.

## How to Access Skills

Use the `skill` tool to invoke skills. Platform-specific: Claude Code=Copilot CLI=`skill`, Gemini CLI=`activate_skill`.

# Using Skills

## The Rule

**Invoke relevant or requested skills BEFORE any response or action.** Even a 1% chance a skill might apply means you should invoke the skill to check. If an invoked skill turns out to be wrong for the situation, you don't need to use it.

## Flow

1. User message received → 2. Check skills (even 1% chance) → 3. Invoke skill tool → 4. If skill has checklist, create todos → 5. Follow skill → 6. Respond

## Red Flags

Stop if you think: "just a simple question", "need more context first", "explore codebase first", "check git/files quickly", "gather information first", "doesn't need a formal skill", "I remember this skill", "doesn't count as a task", "skill is overkill", "just do one thing first", "this feels productive", "I know what that means". These are rationalizations. Check skills FIRST.

## Skill Priority

When multiple skills could apply:

1. **Process skills first** (brainstorming, debugging) — determine HOW to approach
2. **Implementation skills second** (frontend-design, mcp-builder) — guide execution

"Let's build X" → brainstorming first, then implementation. "Fix this bug" → debugging first, then domain-specific.

## Skill Types

**Rigid** (TDD, debugging): Follow exactly. Don't adapt away discipline.

**Flexible** (patterns): Adapt principles to context.

The skill itself tells you which.

## User Instructions

Instructions say WHAT, not HOW. "Add X" or "Fix Y" doesn't mean skip workflows.

**Tool Mapping for OpenCode:**
When skills reference tools you don't have, substitute OpenCode equivalents:
- `TodoWrite` → `todowrite`
- `Task` tool with subagents → Use OpenCode's subagent system (@mention)
- `Skill` tool → OpenCode's native `skill` tool
- `Read`, `Write`, `Edit`, `Bash` → Your native tools

Use OpenCode's native `skill` tool to list and load skills.
