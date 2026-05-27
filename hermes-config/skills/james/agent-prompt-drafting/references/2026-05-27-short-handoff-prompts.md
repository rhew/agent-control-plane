# 2026-05-27 Short Handoff Prompt Correction

James asked for a prompt to update `.gitignore` and check in new Hermes agent state. The first draft was too long and checklist-like. James corrected it with: “Make it short and sweet.”

Durable lesson: for prompts meant to hand to another agent, default to concise, copy-ready instructions. Include the goal, key paths, guardrails, and expected commit or output. Do not expand into a full workflow unless James asks for detail.

Example compact shape:

```text
Update `.gitignore` so we can track James-owned Hermes state while keeping runtime junk ignored.

Track:
- `SOUL.md`
- `memories/MEMORY.md`
- `memories/USER.md`
- `skills/james/`

Keep ignoring secrets, auth files, logs, sessions, caches, request dumps, runtime DBs, and `memories/*.lock`.

Stage only those changes, review `git diff --cached` for secrets or junk, then commit:
`Checkpoint James agent persona and local skills`
```
