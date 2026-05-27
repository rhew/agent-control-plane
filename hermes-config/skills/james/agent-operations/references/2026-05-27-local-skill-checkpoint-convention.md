# 2026-05-27 local skill checkpoint convention

James asked for a path or naming convention that makes it clear which skills were developed locally versus which ones came with Hermes.

Chosen convention:

```text
/opt/data/skills/james/<short-name>/
```

Use this for James-developed, profile-local skills. Keep bundled, hub-installed, or upstream Hermes skills in their existing category paths.

Applied examples:

```text
/opt/data/skills/james/writing-standards/
/opt/data/skills/james/agent-operations/
```

Supporting convention:

- Do not add `james-` to every frontmatter skill name when the path already shows ownership.
- Put session-specific notes in `references/` under the umbrella skill.
- Put reusable starter material in `templates/`.
- Put deterministic commands or probes in `scripts/`.
- When checkpointing local behavior, include `/opt/data/skills/james/` as a directory and preserve removals from older scattered paths.

Checkpoint shape from this session:

```text
/opt/data/SOUL.md
/opt/data/memories/MEMORY.md
/opt/data/memories/USER.md
/opt/data/skills/james/
/opt/data/skills/github/rhew-org-standards/SKILL.md
```

Preserve removals when supported by the checkpoint mechanism:

```text
/opt/data/skills/creative/james-writing-standards/
/opt/data/skills/productivity/james-agent-operations/
/opt/data/skills/creative/bucka-writing-standards/
```
