---
name: content-writer
description: Draft an article from an approved topic for Medium, Substack or a blog: research, a thesis-first draft in the author's voice, diagrams, and a review-ready delivery with notes for the editor. Use after a topic is approved.
---

# Content writer

Turns one approved topic into a draft the author can review and publish. The author is the editor and publisher; this skill never publishes.

Before drafting, load the author's voice skill (for example `yourname-voice`) and a slop-removal skill if you have one. Read `config/publication.md` for the platform, workspace and format.

## Steps

1. **Check approval.** Find the line starting `APPROVED:` in today's proposals. If it is empty, or the day is already drafted or published, stop and change nothing. `APPROVED: custom: ...` means use the author's text as topic and angle.
2. **Research.** Open the proposal links, then find 5 to 10 sources. Prefer primary sources (announcements, docs, filings, reports). Include at least two practitioner or analyst voices with data, not only vendor posts. Record title, publisher, date, URL and the fact used from each. Flag vendor-authored or sponsored sources.
3. **Handle blocked sources honestly.** If a page is blocked or needs a login, find the same story elsewhere or the primary source another way. Never use scrapers, caches or mirrors. Note the substitute in the review notes.
4. **Verify.** Every number, date, name and quote traces to a recorded source.
5. **Thesis first.** Write three lines before outlining: what the title promises, what changes, and who benefits and how. Every section must deliver one of them.
6. **Draft** in the author's voice, at the length set in the voice skill.
7. **Diagrams.** Two or three that show the argument (see below).
8. **Edit pass.** Voice checklist, slop check, and "Before delivery".
9. **Deliver** (see below).

## Writing rules

- **The argument is the structure.** Companies and products are evidence inside sections. If the outline reads "Vendor A, then Vendor B", restructure it around what changes.
- **Headings state claims.** A reader skimming only the headings should get the argument. Avoid generic labels ("Background", "What changed", "Why it matters", "Conclusion").
- **Name things.** Name the product, the person, the request and the result. A sentence that sounds finished but leaves the reader asking "which one?" gets rewritten.
- **Evidence for benefits.** Each claimed benefit carries a number or a named case, or it is cut.
- **Define terms** in one plain clause on first use.
- **Plain examples.** Worked examples use everyday steps the reader would recognise.
- **Label hypotheticals** and give them no invented numbers.
- **Never invent** experiences, results or quotes for the author.

## Template

| Block | Job |
|---|---|
| Opening | News hook, then the thesis: what changes and for whom |
| Image 1 | The shift, before and after |
| One section per "what changes" | Claim heading; mechanism, named evidence, consequence |
| Worked example | Real tasks with and without the shift, then who gains, with evidence |
| Image 2 | What changes, row by row |
| Limits | Inside the relevant section: costs, missing evidence, counter-argument |
| Practical steps | Labeled bullets, only if real steps exist |
| Image 3 | A framework or decision (optional) |
| Close | The implication or the open question |

## Diagrams

- Each diagram shows part of the argument, not logos or decoration. Every box and arrow carries a fact from the draft.
- Use one consistent design system for every image: define its font, colours, icon set and spacing in `config/design.md`, embed the font so the render never falls back to a system default, and keep the source file next to the PNG.
- Look at every PNG before shipping: arrows reach their boxes, no label crosses a line.
- Chart only data from a named source and label the source on the image.

## Platform notes

| Platform | Notes |
|---|---|
| Medium | H2 headings only, captions under images, 4 to 5 tags, no Mermaid (ship PNG) |
| Substack | Subtitle and email preview text matter; keep the first screen strong; images inline |
| Blog (Markdown) | Front matter (title, date, tags, description); alt text on every image |

## Delivery

- Put the article alone where the author reviews it: a new tab in the month's Google Doc, or a new Markdown file. Title, subtitle, body, image captions, sources. Nothing else.
- For revisions, create a new version (tab or file) so the author's comments stay attached to the old one.
- Send the review notes separately (chat or a notes file).

## Before delivery

- [ ] The article answers the title's promise.
- [ ] Headings read alone tell the argument.
- [ ] Products, people and requests are named.
- [ ] Each benefit has a number or named case; two or more practitioner or analyst sources.
- [ ] Terms defined; hypotheticals labeled.
- [ ] Diagrams rendered, checked and captioned in place.

## Review notes (to the author, not in the article)

1. Claims to verify, each with its source link
2. Vendor-authored or single-source claims
3. Images and where each goes
4. Two alternative titles, tags and a short social blurb
5. Anything the author must decide

## Guardrails

- Drafting only. Never publish or message anyone else.
- Short quotes (under 15 words) with attribution; paraphrase the rest.
- Public information only.
