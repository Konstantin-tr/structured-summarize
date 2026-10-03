---
name: structured-summarize
description: Restructure long AI text, articles, and notes into a scannable header tree. Use when asked to summarize, condense, make scannable, rewrite as headers and bullets, or strip waffle without losing meaning.
metadata:
  version: "2.0"
  author: konstantin
---

# Structured Summarize

Restructure source text. Do not write a shorter essay.

Read `references/examples.md` before writing if the shape is unclear.

## Hard rules

- Keep names, numbers, dates, file paths, symbols, constraints, and decisions.
- Drop throat-clearing, hedges, and repeated restatements.
- Do not invent facts, files, or next steps.
- Do not moralize or add advice unless the source already contains it.
- Match the source language.
- Output markdown only. No preamble such as Here is a summary.

## Shape

```md
# <short name of the thing>

## <segment>
<optional intention line>
- fragment
  - child
- parent => consequence

WARNING:
- load-bearing constraint
```

### Headers

- H1 = the thing itself. Never Summary, Overview of X, or Key takeaways.
- H2 = job of that block (Context, Mechanism, Decision, Blockers, Result). Derive from content, do not force a fixed outline.
- H3 only when one H2 would otherwise mix two jobs.
- 2-5 H2s for a short source. Add more only if the source has more distinct jobs.

### Intention line

One short fragment under a header when the bullets need a frame.

Good:

- Successful transformations are
- Therefore, leaders must =>
- Without above elements =>

Bad:

- a full topic sentence that already says what the bullets say
- This section explains...

### Bullets

- Fragments, not sentences. Drop articles and filler verbs when meaning stays.
- Nest for hierarchy. Sibling bullets are parallel.
- Use => for cause to effect or therefore.
- Inline code for identifiers (file paths, symbols).
- One idea per bullet. Split "and also" into a child or a sibling.
- CAPS only on one or two load-bearing words inside a bullet (ESSENTIAL, DO NOT MERGE).

### Callouts

A callout is `LABEL:` on its own line, then nested bullets.

Pick the label from the content. Not always `NOTE`.

- constraint / aside => `NOTE`
- risk / do-not-miss => `WARNING`
- what happened after => `RESULT` or `OUTCOME`
- stop condition => `BLOCKER`
- anything else that is the actual job of the highlight => that word, CAPS

Use a callout only when it earns the highlight. Skip it when the bullets already carry the point. Do not invent one for decoration.

### Density

- If a bullet restates its parent, delete it.
- If two bullets share a subject, nest them under that subject.
- If the source is already short and structured, tighten wording. Do not add headers for sport.

## Anti-patterns

- Executive-summary paragraph plus bullets
- In conclusion
- Recreating the original section order when jobs differ
- Turning a short note into a 20-line tree
- Padding with process language
