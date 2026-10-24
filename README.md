![Plainspoken](images/banner.webp)

# Plainspoken

Plainspoken is a skill for AI coding agents that helps you write technical articles, blog posts, dev notes, docs, and READMEs. Its aim is fairly simple: what comes out should read as though it was written by someone who understands the subject, in that person's own voice, rather than like the text a model produces when it is left to fill space.

## Install

Plainspoken works in Claude Code, in Codex, and in any other agent that reads skills.

In Claude Code (version 2.1.275 or later), run this inside a session:

```
/plugin install plainspoken --marketplace omrajguru/plainspoken
```

On an earlier version, add the marketplace with `/plugin marketplace add omrajguru/plainspoken`, then install it with `/plugin install plainspoken@omrajguru`.

In Codex, add the marketplace and then the plugin:

```bash
codex plugin marketplace add omrajguru/plainspoken
```

```bash
codex plugin add plainspoken@omrajguru
```

For Cursor, Windsurf, and other agents, the skills installer copies the skill into the right folder:

```bash
npx skills add omrajguru/plainspoken
```

Plainspoken is also listed on [skills.sh](https://www.skills.sh/omrajguru/plainspoken/plainspoken).

If you would rather not use any installer, copy `skills/plainspoken` into your agent's skills folder.

## Why it exists

AI-assisted writing tends to go wrong in two places, and only one of them is the language. The language is the problem most people notice: "delve", "seamless", "unlock", a rhetorical question at the start and a summary of everything at the end. Readers have learned to recognise it, and once they do, they stop trusting the rest of the text.

The second problem is less visible and, I think, considerably more damaging. A model will write confidently about things the author does not actually understand. It reads a diff, supplies a plausible reason for the change, and presents that reason as fact. The prose can be perfectly clean and the article can still be wrong, and nobody notices until a reader copies the wrong idea into their own work.

Most tools aimed at "AI slop" deal only with the first problem. Plainspoken treats the second as the more important one, which is why it asks questions before it writes anything.

## What the difference looks like

Here is a paragraph of the kind Plainspoken is meant to prevent:

> In today's fast-paced development landscape, build times play a crucial role in developer productivity. Let's dive into how I leveraged caching to unlock a seamless CI experience. The result? Builds that are 4x faster!

And here is what it aims for instead:

> Our CI build took 14 minutes. Most of that time went into reinstalling dependencies that had not changed, because the cache key included the commit hash. Keying the cache on the lockfile instead brought the median build to 3 minutes and 40 seconds across the last 50 runs.

The second paragraph says what was wrong, why it was happening, what changed, and how the number was measured. It also does not ask the reader to be impressed, which is usually a good sign that the work can stand on its own.

## It learns how you write before it writes anything

The first time you use Plainspoken, it offers a short setup to learn your voice. You can share one to three things you have written, and it will tell you what it noticed (how you open a piece, how sure you sound, which punctuation you use) so that you only have to confirm or correct it. If you would rather not share anything, it asks up to three short rounds of questions instead.

Most of those questions ask you to pick the sentence that sounds most like you, rather than describe your own style. People recognise their voice far more easily than they can explain it, and a sentence you picked teaches the model more than an adjective such as "direct" or "friendly" ever could. Every question can be skipped, and the whole setup takes about five minutes.

The result is a short file saved to `~/.plainspoken/voice.md`, which you can read and edit like any other file. A repository can have its own voice in `.plainspoken/voice.md`, and asking Plainspoken to change your voice updates it later. There is an [example voice file](skills/plainspoken/assets/voice-example.md) if you would like to see what one looks like.

## It asks before it writes

For an article written from your own work, Plainspoken first collects what it can verify (commits, files, numbers, logs) and marks everything else as either its own inference or something only you can answer. It then asks about the gaps, a few questions at a time, each with three possible answers, an explanation of what each one implies, and a recommendation:

```
❓ Q2 · Decision · Why keep filters in the URL
The search page used to keep its filters in component state. The change moved them into URL parameters.

- A) URL parameters: filters survive reloads and shared links; the cost is encoding them on every change.
- B) Component state: simpler, but filters are lost on reload and cannot be shared.
- C) A global store: shared across pages, but it adds a dependency and still loses state on reload.
- D) I can't explain this yet: the point stays out of the article.

➡️ Recommended: A, because the bug reports were about filters lost after a reload.
```

You can answer in shorthand (`1A 2C 3D`). Choosing D is not a failure. It simply means the point is not ready, and it stays out of the article rather than being filled in with a guess.

Links, names, quotes, and sensitive numbers are approved one at a time before they appear. The full draft is shown in chat with a short self-check underneath, and the file is written only after you approve it, in whatever format your repository already uses. If you only want an existing draft tidied, Plainspoken uses a quicker path that asks at most three questions and shows you what it changed.

## The rules depend on what you are writing

A reference page and a dev note should not follow the same rules. Reference should be dry, complete, and certain, whereas a dev note is better for having an opinion and the occasional honest "I suspect". Plainspoken therefore decides what kind of document it is writing before anything else, using the four modes of [Diátaxis](https://diataxis.fr/) (tutorial, how-to, reference, explanation) and a fifth, narrative, for the case studies and write-ups that most technical blog posts actually are. The mode then decides how strictly the clarity rules apply and how much of your voice comes through.

Above every rule sits one that overrides them all: when a rule makes a sentence worse, fix the sentence another way or leave it alone. A piece that obeys every rule and still reads as though a machine wrote it has not succeeded.

## Credits and contributing

The clarity rules draw on the [Google developer documentation style guide](https://developers.google.com/style), [ASD-STE100 Simplified Technical English](https://www.asd-ste100.org/), and *The Global English Style Guide* by John R. Kohl. Everything is written in this repository's own words.

If you notice a pattern that the [slop catalog](skills/plainspoken/references/slop.md) misses, a pull request is welcome. Please include the pattern, what it usually means, and what to write instead.

## Contact

Plainspoken is made by Om. I write on [my website](https://omrajguru.com) and on [Substack](https://omrajguru.substack.com), and I am on [X](https://x.com/NotOmRajguru) as well. For anything else, you can write to me at [hi@omrajguru.in](mailto:hi@omrajguru.in).

Plainspoken is released under the [MIT License](LICENSE).
