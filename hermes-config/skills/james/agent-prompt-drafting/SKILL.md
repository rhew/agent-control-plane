---
name: agent-prompt-drafting
description: Use when drafting prompts for another agent, subagent, or future Hermes session. Produces concise, copy-ready handoff prompts with only the necessary goal, context, guardrails, and expected output.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [james, prompts, handoff, agents, concise]
    related_skills: [james-agent-operations, github-pr-workflow]
---

# Agent Prompt Drafting

## Overview

Use this skill when James asks for a prompt to give another agent or future session. The prompt should save James time, not become a full operations manual. Prefer concise, copy-ready text that lets the next agent inspect live state itself.

This skill captures James's correction from this session: when he asks for a prompt, especially after saying “short and sweet,” do not over-expand into a long checklist.

## When to Use

Use this skill when James asks for:

- A prompt for another Hermes agent.
- A prompt to update files, make a commit, or create a PR.
- A handoff prompt after a checkpoint or context change.
- A shorter version of a previous operational prompt.

Do not use this for full implementation plans unless James asks for a detailed plan.

## Prompt Shape

Default to a fenced block with direct instructions:

```text
Update <thing> so <goal>.

Track/include:
- <path or item>

Keep ignoring/avoid:
- <guardrail>

Stage only those changes, review the diff, and commit:
`<commit message>`
```

Keep it short. Include only:

1. Goal.
2. Key paths or files.
3. Guardrails, especially secrets or unwanted files.
4. Expected output, such as a commit message or PR title.

## Style Rules

- Make it copy-ready.
- Avoid preambles.
- Avoid long numbered workflows unless James asks.
- Do not explain why each step exists.
- Let the next agent inspect current state.
- If James says “short and sweet,” return only the prompt text or a minimal fenced block.

## Common Pitfalls

1. **Turning a prompt into a checklist.** The next agent can run `git status`, inspect `.gitignore`, and review diffs. Do not spell out every tool call unless needed.
2. **Including stale session detail.** Keep durable paths and rules, not a narrative of how we got there.
3. **Forgetting guardrails.** Briefly name what not to commit: secrets, logs, sessions, caches, lock files, request dumps, and runtime databases.
4. **Overexplaining.** James asked for something he can paste, not a tutorial.

## References

- `references/2026-05-27-short-handoff-prompts.md` captures the session correction that established the concise default for handoff prompts.

## Verification Checklist

Before returning a handoff prompt:

- [ ] It is copy-ready.
- [ ] It is short by default.
- [ ] It includes key paths, guardrails, and expected output.
- [ ] It avoids unsupported facts and stale task narrative.
- [ ] It follows James's writing defaults: no em dashes, active voice, concrete wording.
