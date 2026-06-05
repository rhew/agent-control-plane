---
name: rhew-org-standards
description: Use when editing, writing, reviewing, or creating pull requests for rhew/rhew.org. Captures repository-specific commit, Hugo, Markdown, tag, and article voice conventions.
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [github, hugo, markdown, writing, rhew-org, conventions]
    related_skills: [github-pr-workflow, github-repo-management]
---

# rhew/rhew.org Repository Standards

## Overview

Use this skill when working on `rhew/rhew.org`, especially when creating commits, adding Hugo posts, editing Markdown, or preparing pull requests. The site mixes project documentation, recipes, personal posts, memorial writing, and a recurring retired-supervillain persona. Match the local style instead of applying generic blog or Conventional Commit defaults.

The standards below come from the repository's commit history, `hugo-src/config.toml`, post front matter, tags, and representative articles.

## When to Use

Use this skill for:

- Creating or editing posts under `hugo-src/content/posts/`
- Writing commit messages for the repo
- Drafting PR summaries for content or Hugo changes
- Choosing tags, summaries, covers, and `lastmod`
- Matching the right article voice or persona
- Reviewing AI-generated prose before it lands in the repo

Do not use this as a replacement for live inspection when the repo may have changed. Check current files when making real edits.

## Commit Message Standards

Use the repo's existing commit style, not Conventional Commits.

Pattern:

- Short subject only, usually one line.
- Sentence case or title case.
- No trailing period.
- No `feat:`, `fix:`, `docs:`, or other Conventional Commit prefixes.
- Describe the visible change plainly.
- Imperative or noun phrase both appear, but short practical summaries dominate.

Good examples from repository history:

- `Add Cody memorial post and related pet tags`
- `Use summary front matter consistently`
- `Hide same-day updated date in posts`
- `Add Pagefind search to project pages`
- `Update tags and date`
- `Fix links`
- `Gluten free option for brownies`
- `Keep local Hugo output out of legacy site tree`

Good future examples:

- `Add article about porch repair`
- `Update recipe summary`
- `Fix broken project links`
- `Add cover image for rocket post`
- `Tighten Cody post wording`

Avoid:

- `feat: add new article`
- `docs(content): update markdown`
- Long multi-paragraph commit messages unless the change genuinely needs detail.

## Hugo Structure

Current Hugo content lives here:

```text
hugo-src/content/posts/<slug>/index.md
```

Most posts use Hugo page bundles with colocated images:

```text
hugo-src/content/posts/rocket-mk-i/
  index.md
  rocket-mk-i.jpg
  rocket-mk-i-clean.jpg
  rocket-plans.png
```

Relevant Hugo settings observed in `hugo-src/config.toml`:

- Base URL: `https://rhew.org/projects/`
- Posts permalink format: `/:filename/`
- Section pages disabled: `disableKinds = ["section"]`
- Theme stack: `hugo-video`, `rhew-org-theme`
- Local Hugo output should go to ignored `hugo-local-public/`, not the tracked legacy `site/` tree.

For local static Hugo builds outside Docker, prefer the Makefile target:

```bash
make hugo-local
```

For Hugo's built-in development server, run from `hugo-src/` with an explicit local base URL:

```bash
hugo server --baseURL http://localhost:1313/projects/
```

## Front Matter Standards

Every current post has:

```yaml
---
title: "Title Here"
date: YYYY-MM-DD
summary: "Short summary sentence."
tags:
  - tag-name
---
```

Common optional fields:

```yaml
lastmod: YYYY-MM-DD
cover: image-name.jpg
```

Rules:

- Include `title`, `date`, `summary`, and `tags` on every post.
- Add `cover` when the post has a primary image.
- Add `lastmod` only when an existing article changes materially after publication.
- Use lowercase, hyphenated tags where needed.
- Write `summary` as a human-readable sentence, not a keyword blob.
- Prefer quoted summaries, especially when punctuation, apostrophes, or colons appear.
- Put images next to `index.md` and reference them relatively.

Image example:

```markdown
![Recovered parts after two launches](rocket-mk-i.jpg)
```

## Markdown Standards

General conventions:

- Keep Markdown clean and simple.
- Use `##` for main sections in most posts.
- Avoid duplicating the front matter title as an in-body `# Title` unless matching an older style or a short report format.
- Use fenced code blocks with language labels when helpful.
- Use inline code for filenames, commands, config keys, and technical terms.
- Use normal Markdown links.
- Use short paragraphs.
- Use bullets for reports, lists, and "small things that matter."
- Recipes use structured headings, ingredient lists, and numbered steps.
- For recipe substitutions, keep option wording parallel: base ingredient, `or` specific substitute, then the dietary reason when helpful, such as `for gluten-free` or `for dairy-free`.
- When adding optional mix-ins, add both the ingredient line and the corresponding instruction step, such as folding it in before spreading the batter.

Code block example:

````markdown
```dockerfile
RUN hugo --minify --baseURL "${HUGO_BASEURL}"
```
````

## Article Voices and Personas

There is not one site voice. Pick the mode that matches the topic and tags.

### rhew.org, Code, Terminal, Hugo, and Infrastructure Posts

Examples:

- `Static Search for a Static Site`
- `Blogging with Hugo and Docker`
- `Globat sucks`

Style:

- First person.
- Plainspoken and practical.
- Values simplicity, static files, terminal workflows, Docker, and fewer moving parts.
- Uses mild humor, but not too much.
- Explains what changed and why it matters.
- Common rhythm: problem, chosen tool, implementation shape, small details, result.

Representative voice:

> I like static sites because they stay out of the way. Write Markdown, render HTML, let Caddy serve files, and avoid waking up a database just to show somebody a recipe for pizza dough.

Use this style for infrastructure, Hugo, Docker, search, and site-maintenance posts.

### Supervillainy, Retirement, and Maker Posts

Examples:

- `Paper Towel Tube Rocket Mk I`
- `Frontier Airlines`
- `Foam slicer`
- `Retirement Shenanigans`
- `VCF Repair Workshop`

Style:

- Playful retired-overlord persona.
- Uses concrete terms like "minions," "lair," "villainy," "schemes," "henchling," "world domination," and "diabolical."
- Still grounded in real project details.
- Best when jokes ride on concrete facts, not generic villain filler.
- Often uses field-report or dossier structure.

Useful structures:

```markdown
## Design dossier

- Airframe: ...
- Propulsion: ...
- Structure: ...
```

```markdown
## Field report
```

Use this style for rockets, 3D printing, crafts, AI toys, retirement adventures, and absurd project writeups.

### Recipes

Examples:

- `Free Lasagna`
- `Gummy’s Brownies`
- `Base Pan Pizza Recipe`
- `Crab Pizza`

Style:

- Practical and structured.
- Clear title and summary.
- Ingredient lists with quantities.
- Steps in numbered lists.
- Notes for servings, pan size, timing, substitutions, and adaptation source.
- Minimal comedy. Keep it useful.

Common structure:

```markdown
## Recipe Name

*Serves 6 — Fits in an 11×7 inch baking dish*

### Ingredients

#### Component

- item
- item

---

### Instructions

1. **Action** details.
2. **Action** details.
```

Prioritize accuracy and repeatability over voice.

### Memorial, Pets, and Family Posts

Example:

- `Cody Is Love`

Style:

- Restrained, sincere, and concrete.
- Short paragraphs.
- Strong opening sentence.
- Specific memories rather than abstract sentiment.
- Avoid jokes unless they are very gentle and true to the subject.
- Let emotion come from details.

Representative moves:

- "Cody chose Lori first."
- "Cody chose me later that same night."
- "There is no good sentence for that."

Use this style for pets, family, remembrance, and sincere personal posts.

### Practical Personal Records

Example:

- `Exterior Colors and Selections`

Style:

- Direct, factual, and list-oriented.
- Uses headings per item.
- Includes product names, colors, and images.
- Written for review or reference, not entertainment.

Use this style for renovation, selections, HOA-style notes, and reference posts.

## Tag Standards

Common recurring tags include:

- `supervillainy`
- `retirement`
- `recipes`
- `lori`
- `terminal`
- `rockets`
- `ai`
- `crafts`
- `code`
- `docker`
- `cats`
- `3d-printing`
- `rhew.org`
- `hugo`

Guidelines:

- Reuse existing tags before inventing new ones.
- Use specific tags when useful, but keep the first tag aligned with the main category.
- For site/code posts, use some mix of `rhew.org`, `code`, `terminal`, `hugo`, and `docker`.
- For playful project posts, usually include `supervillainy` plus relevant project tags like `rockets`, `3d-printing`, `ai`, or `crafts`.
- For personal, family, and pet posts, use concrete names as tags when already present.

## Pull Request Standards

When creating PRs against this repo:

1. Match the repo's short, direct commit subject style.
2. Put content under `hugo-src/content/posts/<slug>/index.md`.
3. Use full front matter with `title`, `date`, `summary`, and `tags`.
4. Add `cover` when there is a primary image.
5. Add `lastmod` only for meaningful updates to an existing post.
6. Match the article persona to the tag and topic.
7. Avoid generic AI prose.
8. Keep humor concrete and specific.
9. Preserve James's voice over polishing it into bland blog copy.
10. Verify the Hugo build path does not write generated output into the tracked legacy `site/` tree.

### Removing or retiring old functionality

When James asks to remove unused site functionality, distinguish between runtime code and historical content:

- Remove the services, config, secrets references, generated/sample assets, and README steps that keep the unused functionality alive.
- Do **not** delete an existing article about the project unless James explicitly asks for content removal.
- If the article would become misleading, update it instead: add `lastmod`, revise the summary, and make the body clear that the project or site integration is archived/no longer running.
- Keep the archived article in the same voice as the original topic. For code or supervillainy posts, use first-person plainspoken explanation with light concrete humor, not a sterile deprecation notice.
11. When removing site functionality, separate runtime/config removal from published article/content removal. Do not delete a post just because it describes the deprecated feature unless James explicitly asks to remove the published post too.

## Common Pitfalls

1. **Using Conventional Commits.** This repo does not use them. Prefer `Fix links` over `fix: repair broken links`.
2. **Flattening the voice.** The site relies on distinct modes. Recipes, memorials, supervillain posts, and code posts should not sound alike.
3. **Overdoing the villain persona.** Concrete details make the joke work. Generic villain filler weakens the post.
4. **Adding `lastmod` for trivial edits.** Use it for meaningful updates, not typo-only changes unless the repo owner asks otherwise.
5. **Inventing tags too quickly.** Reuse existing tags first.
6. **Duplicating titles as H1s by default.** Most posts rely on front matter title and begin with body copy or `##` sections.
7. **Writing generic recipe prose.** Recipes need accurate quantities, timing, substitutions, and steps more than flourish.
8. **Letting local Hugo output pollute tracked files.** Use `make hugo-local` for local static builds.
9. **Rewriting historical project posts during cleanup.** When removing old site functionality, keep posts that record what was built. Add a short dated update only when it clearly matches the remaining article and does not distort the original record. Do not delete the article or rewrite it as if it were only current documentation.

## Verification Checklist

Before committing changes:

- [ ] Commit subject matches existing short repo style.
- [ ] New post lives in `hugo-src/content/posts/<slug>/index.md`.
- [ ] Front matter includes `title`, `date`, `summary`, and `tags`.
- [ ] `cover` points to a colocated image if used.
- [ ] `lastmod` appears only when appropriate.
- [ ] Tags reuse existing vocabulary where possible.
- [ ] Markdown image paths are relative to the page bundle.
- [ ] Article voice matches topic: code, supervillainy, recipe, memorial, or practical record.
- [ ] Generated Hugo output is not accidentally staged.
- [ ] Any build or local verification follows the repo README and Makefile.
