---
name: james-writing-standards
description: Use when drafting, editing, reviewing, or humanizing writing for James across contexts. Captures durable voice, clarity, anti-slop, tone, and persona-selection practices that apply beyond rhew/rhew.org.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [writing, editing, voice, james, anti-ai-slop, style]
    related_skills: [humanizer, rhew-org-standards]
---

# James Writing Standards

## Overview

Use this skill for James's writing outside any one repo: emails, Discord messages, blog posts, PR descriptions, contractor messages, family notes, documentation, and article drafts. It reconciles the site-specific `rhew-org-standards` skill with the broader `humanizer` skill so James's favorite practices travel everywhere.

The core rule: preserve James's voice and save his time. Tighten, clarify, and de-slop. Do not polish everything into the same bland assistant voice.

## When to Use

Use this skill when James asks you to:

- Draft or edit any message, article, post, PR description, note, or document
- Humanize, de-AI, tighten, or make writing sound more like him
- Adapt a piece for a specific audience
- Review writing before publishing or sending
- Carry rhew.org-style practices into other contexts

Also use it as a final pass on your own user-facing prose when the response itself is writing assistance.

## Universal Writing Rules

Apply these unless James asks for a different style:

- Be clear, direct, and concrete.
- Use active voice unless passive voice clearly improves the sentence.
- Use the Oxford comma.
- Do not use em dashes.
- Avoid corporate filler.
- Avoid influencer voice.
- Avoid inflated importance.
- Avoid fake enthusiasm.
- Preserve the intended tone and recipient relationship.
- Do not add unsupported facts, claims, implications, or emotional stakes.
- Prefer specific details over abstract claims.
- Prefer short, useful sentences over polished-sounding paragraphs.
- Leave some human rhythm in the prose. Perfect symmetry sounds generated.

## Anti-Slop Standards

Use `humanizer` as the broad anti-AI checklist. James's most important defaults:

- Remove chatbot artifacts: "Of course," "Great question," "I hope this helps," and "Let me know if..."
- Remove significance inflation: "pivotal," "crucial," "testament," "underscores," "landscape," and similar puffery.
- Remove generic conclusions: "the future looks bright," "exciting times ahead," and "a step in the right direction."
- Remove signposting that delays the point: "Let's dive in," "Here's what you need to know," and "Let's break this down."
- Replace vague authorities with specifics or delete them.
- Replace abstract business language with plain language.
- Do not force a rule of three.
- Do not cycle synonyms to avoid natural repetition.
- Do not overuse bold, emoji, title-case headings, or inline-header bullet lists.
- Avoid "not just X, but Y" unless it is genuinely the cleanest construction.

## Voice Selection

Do not apply one voice everywhere. Pick the mode that fits the job.

### Clear professional

Use for contractors, professional coordination, logistics, vendors, and issue resolution.

Traits:

- Direct and non-confrontational.
- Friendly only where it helps.
- Clear ask, clear facts, clear next step.
- No sarcasm unless James explicitly asks for it.
- Avoid legalistic or threatening language unless he asks.

Shape:

```text
Hi [Name],

[Plain context.]

[Specific request or decision needed.]

[Deadline or next step, if relevant.]

Thanks,
James
```

### Family and personal

Use for family messages, personal updates, and anything emotionally sensitive.

Traits:

- Warm but not syrupy.
- Concrete details over generic sentiment.
- Respect the relationship.
- Keep jokes gentle and specific.
- Do not over-explain feelings.

### Practical technical

Use for docs, repo notes, PR descriptions, troubleshooting notes, and technical summaries.

Traits:

- First state what changed or what matters.
- Use bullets when they reduce reading time.
- Include commands, paths, versions, and exact constraints when relevant.
- Avoid tutorial-script framing.
- Prefer "what changed / why / how verified" over narrative filler.

PR description shape:

```markdown
## Summary
- ...
- ...

## Test plan
- ...
```

Only add sections that help the reviewer.

### Plainspoken essay or article

Use for reflective posts, site updates, project writeups, or longer explanations.

Traits:

- First person is fine when the piece is personal.
- Start with a real thought, not a throat-clearing intro.
- Explain the problem, the choice, the result, and the small details that mattered.
- Mild humor works when it comes from concrete facts.
- Avoid moralizing and generic takeaways.

### Playful persona

Use only when the context supports it, such as rhew.org supervillainy, maker shenanigans, rockets, retirement adventures, and absurd project writeups.

Traits:

- Make the joke ride on facts.
- Use persona terms sparingly enough that they stay funny.
- Keep the real project or event legible.
- Do not paste villain vocabulary onto unrelated topics.

### Sincere memorial or grief writing

Use for pets, family, loss, and remembrance.

Traits:

- Restrained, sincere, and concrete.
- Short paragraphs.
- Strong opening sentence.
- Specific memories instead of broad claims.
- Avoid jokes unless they are gentle, true, and already part of the relationship.
- Let emotion come from the details.

## Editing Workflow

1. Identify the recipient, context, and goal.
2. Choose the voice mode before rewriting.
3. Preserve facts and intent.
4. Cut filler and unsupported claims.
5. Tighten sentence structure.
6. Restore human rhythm where the edit got too smooth.
7. Check for James's defaults: no em dashes, active voice, Oxford comma, concrete details.
8. If editing for an external recipient, keep the tone clear, direct, and non-confrontational.

## What to Preserve

Do not erase these when editing James's writing:

- Dry humor
- Practical bluntness
- First-person perspective
- Specific names, places, objects, and constraints
- Natural repetition when it sounds like a person talking
- Short punchy sentences
- A little mess when it makes the voice more honest

## What to Remove

Cut or rewrite:

- Generic openings
- Boilerplate transitions
- Abstract praise
- Unsupported certainty
- Vague emotion
- Corporate politeness padding
- Assistant-like helpfulness signals
- Overexplained jokes
- Unnecessary softeners that hide the ask
- Excessive polish that makes the piece sound less like James

## Relationship to rhew.org Standards

`rhew-org-standards` applies to one repo and one site. This skill applies everywhere.

Carry these repo-derived practices into broader writing:

- Match the persona to the piece.
- Prefer concrete details to generic polish.
- Keep humor grounded in facts.
- Use practical structure when the content is practical.
- Treat recipes, memorials, technical posts, and playful articles as different writing modes.
- Preserve James's voice over making the prose universally smooth.

Do not carry repo-specific mechanics everywhere:

- Hugo front matter belongs to Hugo posts only.
- rhew.org tags belong to that site only.
- rhew.org commit style belongs to that repo unless another repo matches it.

## Common Pitfalls

1. **Over-humanizing into someone else's voice.** Add life, but do not turn James into a columnist, marketer, or influencer.
2. **Flattening all modes.** A contractor message, recipe, memorial, and supervillain post should not sound alike.
3. **Keeping assistant scaffolding.** Remove "here's a revised version" from content meant to be sent or published.
4. **Adding claims to improve flow.** If James did not provide a fact, do not invent it.
5. **Over-softening direct asks.** Polite is good. Mushy is not.
6. **Overusing bullets.** Bullets save time for logistics and technical summaries, but they can drain voice from personal writing.
7. **Overdoing jokes.** One concrete joke usually beats three generic ones.
8. **Leaving em dashes.** James's default writing rule forbids them.

## Verification Checklist

Before returning writing to James:

- [ ] The draft fits the recipient and purpose.
- [ ] The chosen voice mode is intentional.
- [ ] The text contains no em dashes.
- [ ] Active voice carries the main actions.
- [ ] Lists use the Oxford comma where applicable.
- [ ] Generic AI phrases and chatbot artifacts are gone.
- [ ] Unsupported claims are removed or clearly marked as assumptions.
- [ ] Humor, if present, comes from concrete facts.
- [ ] The edit sounds like James, not like a polished assistant.
- [ ] The final version is ready to send or publish without extra wrapper text when requested.
