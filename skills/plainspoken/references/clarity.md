# Clarity

Write so a tired reader understands on the first read. These rules draw on the Google developer documentation style guide, ASD-STE100 (Simplified Technical English), and Global English practice, rewritten for articles as well as docs.

Rules marked **(relaxed in explanation and narrative)** may bend in those modes when bending them makes the sentence clearer or more natural. Every other rule applies in every mode.

## Three rules above the rest

- **Cut every word that does no work.** If the sentence survives without a word, the word goes. "In order to" is "to". "It is important to note that" is nothing.
- **Use the short, everyday word.** "Use", not "utilize". "Help", not "facilitate". "Start", not "initiate". A long word has to earn its length with precision.
- **Be specific.** Not "schema changes can cause issues" but "renaming a column fails the build". Not "significantly faster" but "from 14 minutes to 3".

## Words

- **Use the real name.** Write the actual function, file, flag, command, or product name, not a description of it. In code-related writing, the codebase is the word list.
- **Do not invent jargon.** Use the words a developer would say out loud. A named pattern is fine if you say what it means the first time you use it.
- **Explain a term before you rely on it.** Spell out an acronym on first use unless every reader will know it.
- **One name per thing.** If you call something "the cache" once, do not call it "the store" and "the memo layer" later. Three names teach the reader three things.
- **One meaning per word.** If "check" means inspect, do not also use it to mean stop.
- **One word per action.** Pick "start" or "launch" and keep it.
- **No slashes for choices.** Write "A, B, or both", not "A/B" or "and/or".
- **No "(s)" plurals.** Write "one or more files", not "file(s)".
- **Drop "etc."** If a list is partial, say so before it: "Supported formats include".
- **Avoid idioms and metaphors.** Many readers read English as a second language, and translators trip on them. **(relaxed in explanation and narrative)**: a plain, familiar comparison is fine when it explains something faster than the literal version would.
- **Avoid Latin abbreviations.** "For example", not "e.g.". "That is", not "i.e.".

## Sentences

- **Say who does what.** "The compiler checks the types", not "the types are checked". Use the passive only when the actor is unknown or does not matter.
- **Use the present tense.** Use "will" only for things that really happen later.
- **One thought per sentence.** Split a sentence that carries two. Keep a long sentence that carries one.
- **Watch the length.** Split instructions longer than about 20 words and other sentences longer than about 25. **(relaxed in explanation and narrative)**: a longer sentence is fine if it carries one thought with its condition or consequence.
- **Put the common case first,** then the exceptions.
- **Keep the small words.** Keep "the", "a", and "that" when they prevent a second reading. "Remove backup file" reads two ways. "Remove the backup file" reads one.
- **Keep "only" and "not" next to the word they change.** "Fails only on Windows" and "only fails on Windows" can mean different things.
- **Break up noun stacks.** "The user session token refresh handler" becomes "the handler that refreshes the user's session token".
- **Make every "it", "this", and "they" point at one obvious thing.** Repeat the noun when in doubt. Never use "this" or "which" to point at a whole previous sentence.
- **Do not drop verbs.** "Version 1 moves the parser and version 2 the runtime" leaves version 2 without a verb. Give it one.
- **Make "and" and "or" group one way.** Use "both ... and" or "either ... or" when a sentence could group two ways.
- **Use semicolons sparingly.** Two sentences are usually clearer. **(relaxed in explanation and narrative)** if the voice file allows them.
- **Make parenthetical text a full unit.** Text in parentheses should be a complete phrase or its own sentence.

## Instructions

These apply to every step the reader is meant to follow, in any mode.

- **Write steps as commands.** "Install the package", not "the package should be installed" and not "next, you'll want to install the package".
- **One instruction per sentence.**
- **Put the condition or warning before the step.** "To delete the branch, run `git branch -d`." "If the build fails, check the logs before you retry."
- **Say what the reader should see** after a step that changes something visible.
- **Never call a step simple, easy, or quick.** If it were, the reader would not be reading. Never say "just" or "simply" either.
- **No "please"** in instructions.

## Structure

- **Headings say the point, not just the topic.** "Pick the mode first", not "Modes". Use sentence case. A task heading is a verb phrase ("Create a project"). A concept heading is a noun phrase.
- **One top-level heading per page,** and do not skip heading levels.
- **Numbered lists for sequences, bullets for everything else.** Introduce a list with a complete sentence, and keep the items parallel in form.
- **Use prose when the ideas connect.** A list breaks reasoning into pieces. If each item needs "because" or "so" to make sense, it should be a paragraph.
- **Code in code font. Interface labels in bold.** Use the serial comma.
- **Links say where they go.** Use the page title or a short description, never "click here" or "this link". Prefer a sentence of context on the page over sending the reader off it.
- **Do not pre-announce.** Do not write about features that do not exist yet ("we will soon support").
- **Do not start consecutive sentences the same way.**

## Rhythm

Text can obey every rule above and still read as machine-written: every sentence clipped, nothing specific, no view anywhere.

- **Mix sentence lengths on purpose.** Short sentences land a point. Longer ones carry a fact with its condition or its consequence.
- **Write in paragraphs.** A paragraph holds one piece of reasoning and develops it. Do not make every sentence its own paragraph.
- **Have a view where the mode allows it.** In explanation and narrative, say what you make of the trade-offs.
- **Read it aloud in your head.** If a sentence would sound odd said to a colleague, rewrite it.

## Example

Before:

> Configuration of the retry policy parameters is performed via the config file. It's important to note that increasing the max retries value, which controls how many attempts will be made, should only be done when the upstream is known to be flaky. If exceeded, the job fails.

After:

> The job reads its retry policy from `retry.yaml`. `max_retries` sets how many times the job retries a failed request before it fails. Raise it only for upstream services that fail intermittently.
