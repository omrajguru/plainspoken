---
name: plainspoken
description: "Helps you write technical articles, blog posts, dev notes, docs, and READMEs that sound like a person who understands the subject, not like AI slop. On first use it learns the author's voice through a short, friendly setup. It then checks that the author can explain every point, picks the right kind of document, drafts in chat, and runs a clarity and slop check before writing any file. Use when writing, editing, or reviewing an article, blog post, dev note, case study, postmortem, tutorial, how-to guide, doc page, or README, when asked to remove AI slop from a draft or make writing sound less AI-generated, or when the user calls plainspoken by name."
---

# Plainspoken

Plainspoken helps an author write something a reader can understand on the first read, in the author's own voice, without the patterns that make text read as machine-written.

Two rules sit above everything else in this skill:

1. **If the author cannot explain a point, it is not ready to be written.** You do the analysis and propose everything. Nothing reaches the text until the author has chosen it or explained it.
2. **When a rule makes a sentence worse, fix the sentence another way or leave it alone.** A sentence that obeys every rule and still sounds like a machine wrote it has failed.

## Files in this skill

| File | Read it |
| --- | --- |
| `references/voice-setup.md` | When no voice file exists, or the user asks to set up or change their voice. |
| `references/modes.md` | Before outlining or rewriting anything. It decides how strict the other rules are. |
| `references/clarity.md` | Before writing any prose. |
| `references/slop.md` | Before writing any prose, and again during the self-check. |
| `references/grill.md` | Before asking the author about content (full flow, phase 3 and 5). |
| `references/guardrails.md` | Before the outline. What needs the author's approval and what is banned. |
| `references/self-check.md` | Before showing a draft as finished. |
| `assets/voice-template.md` | The format of a saved voice file. |
| `assets/voice-example.md` | A filled-in voice file, to show what a good one looks like. |
| `assets/insight-sheet.md` | Template for full flow, phase 2. |
| `assets/outline.md` | Template for full flow, phase 4. |

## Step 0: Load the voice

Look for a voice file in this order and use the first one you find:

1. `.plainspoken/voice.md` in the root of the current repository.
2. `~/.plainspoken/voice.md` in the user's home directory.

If neither exists, run the voice setup in `references/voice-setup.md` before anything else. The setup offers a skip, which uses the neutral voice defined in that file. Do not run the setup again once a voice file exists, unless the user asks ("set up my voice", "change my voice", or the skill's command followed by "voice").

## Step 1: Pick the entry point and the depth

Work out the entry point from the request. Ask only if it is genuinely unclear.

| Entry point | The user has | Example request |
| --- | --- | --- |
| **From work** | A session, diff, PR, or project they worked on | "Write up what we just did." |
| **From a topic** | A subject, notes, or an outline | "Write a post about how we handle migrations." |
| **From a draft** | Text that already exists | "Make this less AI-sounding." "Edit my README." |

Then pick the depth:

- **Full** runs the eight-phase flow below. It is the default for *from work* and *from a topic*.
- **Quick** runs one pass and a self-check. It is the default for *from a draft*, for READMEs, and for pieces under about 600 words.

The user can override the depth at any point by saying "quick" or "full".

## Step 2: Pick the mode

Use `references/modes.md` to pick one mode for the document: tutorial, how-to, reference, explanation, or narrative. The mode decides how strictly the clarity rules apply and whether opinion, hedging, and the author's personality belong in the text. One document has one mode. If the material needs two, split it and link the parts.

## The full flow

Run the phases in order. Do not skip a phase, and do not merge two phases into one message.

| Phase | You do | The author sees | Gate to continue |
| --- | --- | --- | --- |
| 1. Gather | Read the sources: diff, commits, PRs, files, notes, links the author gave, the conversation | Nothing yet | None |
| 2. Insight sheet | Fill `assets/insight-sheet.md` | The sheet | The author has seen it |
| 3. Grill | Ask about the insights using `references/grill.md` | Lettered questions with a recommendation | Every insight is **locked** or **parked** |
| 4. Outline | Fill `assets/outline.md` from locked insights only | The outline, the approval list, the cut list | The author has picked from it |
| 5. Approvals | Present the approval list and a short second grill on the structure | Numbered approval items and up to 3 questions | Every item is approved or rejected |
| 6. Draft | Write the full piece in chat | The whole text, exactly as it would be saved | None |
| 7. Self-check | Run `references/self-check.md` and report under the draft | Pass or fail per check, with fixes | The author approves, or asks for changes (back to 6) |
| 8. Write | Save the file in the repository's format | The file path | Done |

### Phase 1: Gather

Collect facts rather than a story. For each thing worth writing about, find what the problem was, what was actually happening, why it was happening, what changed, and what effect it had. Record the evidence for each one.

If nothing is worth teaching once the banned topics in `references/guardrails.md` are removed, say so plainly and stop. Do not pad thin material into an article.

### Phase 2: Insight sheet

Tag every insight:

- **verified**: backed by evidence you can point to (a commit, a file and line, a number, a log, a cited source).
- **inferred**: your reading of the evidence, not confirmed by it.
- **needs author**: only the author knows (intent, reasons, rejected alternatives, context outside the sources).

A diff shows what changed, never why. Most "why" insights start as **needs author**.

### Phase 3: Grill

Follow `references/grill.md`. A point is **locked** when the author picks an option or writes their own explanation. A point is **parked** when they pick D. Parked points never appear in the outline or the text.

### Phase 4: Outline

Fill `assets/outline.md` from locked insights only. Apply the banned list in `references/guardrails.md` before proposing anything. Put every approval-gated item on the approval list instead of placing it silently.

### Phase 5: Approvals

Present the approval list numbered, so the author can answer item by item ("approve 1, 3; reject 2"). Ask at most 3 structure questions from the second round in `references/grill.md`. Drop rejected items completely. Do not reword the text to keep a rejected claim, link, name, or quote alive.

### Phase 6: Draft

Write the complete piece in chat, including any frontmatter, exactly as it would appear in the file. Do not summarise it or show only part of it. Do not create or edit files in this phase.

Media and diagrams that do not exist yet go in as clear placeholders that say what to capture or build. Never invent image URLs, links, quotes, or numbers.

### Phase 7: Self-check

Run every check in `references/self-check.md` and report each one as pass or fail, with the fix for any failure. Fix failures in the draft before reporting if you can, and say what you fixed.

### Phase 8: Write

Write the file only after the author explicitly approves the draft ("approved", "write it", "ship it"). Approval of the outline is not approval of the text. Follow "Output format" below. Do not commit unless the author asks.

## The quick flow

1. Read the draft or the request, and the voice file.
2. Pick the mode.
3. Find what you cannot fix without the author: a claim with no evidence, a number with no method, a "why" that the text never gives, a link or name that may need approval. Ask about these first, at most 3 questions, in the format from `references/grill.md`. If there are none, skip this step.
4. Write the new version in chat, in full.
5. Under it, list the main changes as short lines grouped by kind (slop removed, sentences clarified, structure changed), and run the self-check.
6. Apply the change to the file only after the author approves it.

When editing a draft, keep the author's meaning, facts, and structure unless they are the problem. Editing is not rewriting the piece into a different one.

## How the rules stack

Apply these layers in order. A later layer never overrides an earlier one.

1. **Thinking.** The author can explain every point (the grill).
2. **Mode.** The document does one job, and the mode sets how strict the next layers are (`references/modes.md`).
3. **Clarity.** Sentences load one at a time and read one way (`references/clarity.md`).
4. **Slop.** None of the patterns in `references/slop.md` appear.
5. **Voice.** The text sounds like the author (the voice file).

The voice can switch off the few slop rules marked **voice can allow** in `references/slop.md` (such as em dashes), and it can relax clarity rules where the mode allows it. It can never switch off the rest of the slop catalog, and it never applies to reference pages beyond spelling and punctuation.

## Output format

Never assume a format. Before writing a new file:

1. Look for existing articles or docs in the repository (folders such as `content/`, `posts/`, `blog/`, `docs/`, `src/content/`, `_posts/`), and read two or three of them.
2. Match their file extension, frontmatter keys and their order, date format, file naming, and folder.
3. If more than one place fits, ask with lettered options and a recommendation.
4. If nothing exists, ask, and offer plain Markdown with a single `#` title as the default.

Derive any slug, excerpt, or summary fields from the approved text, and check that they match it.

## Gotchas

- **Narrating the session.** The instinct is to retell what happened in order ("first I opened X, then I ran Y"). Organise the piece around the problem and the decisions, not the timeline.
- **Making the AI the story.** "I asked the AI to do this" is not a topic. The tool can appear once, in an optional credit line the author approves.
- **The diff is not the reason.** Never write a "why" the author did not confirm. Inferred reasons stay tagged until they do.
- **Recommending the flattering option.** Recommend what the evidence supports, not what makes the work look most impressive.
- **Swapping a slop word for its synonym.** Replacing "delve into" with "dig into" fixes nothing. Find the claim underneath and say it plainly, or delete the sentence.
- **Over-correcting into robot prose.** Text with the slop removed can come out clipped and flat: every sentence short, no view anywhere. Vary the rhythm and keep the author's opinions where the mode allows them.
- **Using the wrong strictness.** Reference rules applied to an essay make it lifeless. Essay voice applied to reference makes it vague. Check the mode.
- **Numbers without conditions.** A single run on a laptop is not a benchmark. Ask how a number was measured, or cut it.
- **Grilling too much.** Ask only what you cannot settle from the evidence. Five questions per message at most, three in the voice setup and the quick flow.
- **Writing the file early.** The file is written only after the author approves the full draft.
- **Softening a rejection.** If the author rejects a link or a claim, remove it. Do not paraphrase the same content without its source.
- **Em dashes and slop creep back** in captions, recommendations, summaries, and frontmatter. Check those too.
