# Voice setup

The voice setup runs once, the first time the skill is used and no voice file exists. It produces a short voice file that every later piece follows.

This is not the content grill. The content grill checks whether the author understands something. The voice setup asks about taste, and taste has no wrong answers. Keep it light.

## Rules for the setup

- **Keep it to about five minutes.** At most three rounds, and at most three questions per message.
- **Show sentences instead of asking for descriptions.** "Which of these sounds like you?" is easy to answer. "Describe your tone" is homework. Use sentence options wherever you can.
- **Mark a default, not a recommendation.** It is a preference, so do not argue for one answer.
- **Always offer a way out.** Every question has "D) Skip", which takes the default. The author can say "use defaults for the rest" at any point, and you go straight to the confirm step.
- **Never ask the author to justify an answer.** No "why?" follow-ups on taste.
- **Accept shorthand.** "1B 2A 3C" is a full answer. So is "2B, but I do use semicolons".
- **Be friendly and brief.** One line of framing per round, no lectures about writing.

## Step 0: Offer the setup

Open with one message:

```
Before we write anything: I can learn how you write, so the result sounds like you and not like a template. It takes about five minutes, once.

- A) Share 1 to 3 things you have written (paste them, or give me file paths or links). I work out your voice and you just confirm it. This is the fastest.
- B) Answer a few quick questions instead.
- C) Skip for now and use a neutral voice. You can set it up later by asking me to set up your voice.
```

- **A** goes to "Learning from samples".
- **B** goes to "Round 1".
- **C** saves nothing, uses the neutral voice below for this session, and asks again only if the author asks to set up their voice. To stop the offer repeating, save the neutral voice as the voice file and say where it was saved.

## Learning from samples

Read the samples and note what is consistent across them:

- How pieces open (with the result, the problem, the reader's situation, a story).
- Person ("I", "we", "you") and how often the author appears in the text.
- Contractions, and how formal the sentences are.
- The mix of sentence lengths, and how long paragraphs run.
- How sure the author sounds, and which hedges they use, if any.
- Punctuation habits: em dashes, semicolons, parentheses, exclamation marks.
- Spelling (US or UK).
- Words and phrases the author uses often.
- One or two sentences that sound most like them, to quote in the voice file.

Present what you noticed as at most six numbered lines, then ask only what the samples could not answer (usually the reader, and words the author never wants to see):

```
From your 2 posts, here is what I noticed. Reply "ok", or correct any line by its number.

1. You open with the result and its number.
2. You write as "I", and you use contractions.
3. You hedge with "I think" and "perhaps" when you are unsure, and not otherwise.
4. You use parentheses often and never use em dashes.
5. You use UK spelling.
6. This sounds most like you: "Our build took 14 minutes. I got it to 3, and most of the win came from one cache key."

Two things I could not tell from the samples:

❓ 1 · Who you usually write for
- A) Developers who already know the stack
- B) Developers who are new to the topic
- C) A mixed audience, including people who are not developers
- D) Skip
Default: B

❓ 2 · Words or phrases you never want to see in your writing (up to 5), or "skip".
```

Two rules for samples:

- **Do not copy slop into the voice.** If a sample uses patterns from `references/slop.md`, do not record them as the author's habits. If most of a sample reads that way, say so kindly and suggest a different sample or the questions instead.
- **Use only the author's own writing.** If a sample was clearly written by someone else, ask before using it.

Then go to "Confirm and save".

## Round 1 of 3: Basics

```
Round 1 of 3 · The basics
Pick the one closest to you. Shorthand works: "1A 2B 3A".
```

**Who you write for**

- A) Developers who already know the stack
- B) Developers who are new to the topic
- C) A mixed audience, including people who are not developers
- D) Skip

Default: B

**How you refer to yourself**

- A) "I": it is my work and my view.
- B) "We": I write for a team or a project.
- C) Mostly "you": I keep myself out of it.
- D) Skip

Default: A

**How formal you sound**

- A) "This approach doesn't scale past a few thousand rows."
- B) "This approach does not scale well beyond a few thousand rows."
- C) "Beyond a few thousand rows, this approach becomes impractical."
- D) Skip

Default: A

## Round 2 of 3: How you sound

```
Round 2 of 3 · How you sound
Pick the one closest to you.
```

**How you open a post**

- A) "Our build took 14 minutes. I got it to 3, and most of the win came from one cache key."
- B) "If you have ever waited on a slow CI build, you know the feeling of losing your train of thought."
- C) "I have been working on our build pipeline for the past month, and it has changed how I think about caching."
- D) Skip

Default: A

**How sure you sound**

- A) "Use a lockfile. There is no good reason not to."
- B) "I think a lockfile is worth it in almost every case, although small scripts can probably skip it."
- C) "Lockfiles have trade-offs. Here is what each choice costs, so you can decide."
- D) Skip

Default: B

**Punctuation you actually use**

- A) Em dashes, semicolons, and parentheses are all fine.
- B) Parentheses are fine. No em dashes, and few semicolons.
- C) Plain commas and full stops only.
- D) Skip

Default: B

## Round 3 of 3: Your words

```
Round 3 of 3 · Your words
Last one.
```

**Spelling**

- A) US English
- B) UK English
- C) Something else (say which)
- D) Skip

Default: A

**Words you like and words you never use**

Ask for up to 5 of each, as free text, or "skip". Do not suggest a list. Add any word the author names to the voice file exactly as given.

**What to call you**

- A) My first name
- B) My full name
- C) Never by name
- D) Skip

Default: A. If the author picks A or B, ask for the name in the same message.

## Confirm and save

Fill `assets/voice-template.md` from the answers. Put the sentences the author picked, or the sentences quoted from their samples, under "Sounds like me". Examples teach a model more than adjectives do.

Show the whole file in chat and ask one question:

```
Here is your voice file. Does this sound like you?

<the file>

Reply "save" to save it to ~/.plainspoken/voice.md, which works in every repository. Say "this repo only" to save it to .plainspoken/voice.md here instead. Or correct any line.
```

Save it only after the author replies. Then continue with what they originally asked for.

## The neutral voice

Use this when the author skips the setup, and for any answer they skip.

- **Reader:** developers who are new to the topic.
- **Person:** "I" for the author's own work and views, "you" for the reader.
- **Formality:** plain and conversational, with contractions.
- **Openings:** lead with the result or the point.
- **Certainty:** clear positions; hedge only where the doubt is real.
- **Punctuation:** parentheses are fine; no em dashes; few semicolons.
- **Spelling:** US English.
- **Name:** not used.

## Changing the voice later

When the author asks to change their voice, show the current file and ask what to change. Run a full round only if they ask to start over. Small corrections ("I do use semicolons") are a one-line edit.
