# Slop catalog

Slop is text that sounds like writing but says less than it seems to. It is usually produced by a model filling space, and readers have learned to spot it. One instance is a small cost. A pattern of them makes the reader stop trusting the text.

## How to fix slop

1. Find the pattern.
2. Ask what claim sits underneath it. "This seamless integration unlocks new possibilities" might mean "you can call the API from the CLI now".
3. Write that claim plainly, with the specific thing named.
4. If there is no claim underneath, delete the sentence.

Never swap a slop word for its synonym. "Dig into" is "delve into" in a different coat. Fix the sentence, not the word.

Every pattern below applies in every mode and cannot be switched off by a voice file, except the few marked **voice can allow**.

## 1. Vocabulary

These words and phrases mark text as generated, usually because they replace a specific claim with an atmosphere.

| Avoid | Usually means | Write instead |
| --- | --- | --- |
| delve into, dive into, dig into | look at, explain | Say what you examine: "This post covers how the cache invalidates." Or just start. |
| journey | process, project, time spent | Name it: "the migration", "the three months it took". |
| landscape, realm, world of, space (as in "the AI space") | a field or a set of tools | Name the field or the tools. |
| tapestry, symphony, dance, mosaic | many things together | Say which things and how they relate. |
| seamless, seamlessly | it works without extra steps | Say which steps it removes. Keep "seamless" only for something literally without seams. |
| robust | it handles failure | Say which failures it handles. |
| leverage (as a verb), utilize, harness | use | "Use". |
| unlock, unleash, empower, enable (as hype) | lets you | "Lets you" plus the actual thing. |
| elevate, enhance, supercharge, turbocharge | improve | Say what improved and by how much. |
| streamline | remove steps | Say which steps. |
| reimagine, redefine, revolutionize, transform | change | Say what changed. |
| game-changing, groundbreaking, cutting-edge, next-level, state-of-the-art | new or good | Say what is new about it, or cut the word. |
| crucial, pivotal, vital, essential (as filler) | important | Usually nothing. If it matters, show why. |
| a testament to | shows | "Shows", or cut. |
| plays a key role in, plays a crucial role in | does, affects | Say what it does. |
| ever-evolving, fast-paced, rapidly changing | changing | Usually nothing. |
| in today's world, in this day and age, in the modern era | now | Usually nothing. |
| at the intersection of | involves both | "Uses X and Y", or name the actual overlap. |
| navigate (a problem, a codebase, a challenge) | handle, use, understand | The ordinary verb. |
| foster, cultivate (outside gardening) | encourage, build | The ordinary verb. |
| quietly (as atmosphere) | (nothing) | Cut. "Quietly fixes the bug" is "fixes the bug". |
| magic, magical, wizardry | it works and the reader cannot see how | Explain how it works. |
| powerful, elegant, beautiful (as filler) | good | Say what makes it good, or let the reader decide. |
| comprehensive, holistic, end-to-end (as filler) | covers a lot | Say what it covers. |
| myriad, plethora | many | "Many", or the number. |
| boasts | has | "Has". |
| embark, endeavor (as a verb) | start, try | "Start", "try". |

## 2. Structure

Patterns in how sentences and paragraphs are built.

- **"It's not X, it's Y" and "not just X, but Y".** A false contrast with something nobody claimed. Say what it is.
  - Before: "This isn't just a cache. It's a new way of thinking about state."
  - After: "The cache also stores the session state, so a reload keeps the user's place."
- **Groups of three for rhythm.** "Fast, reliable, and secure." Three items because three sounds finished, not because there are three. Keep only the items that are true and specific.
- **Rhetorical question openings.** "Ever wondered why your build is slow?" Start with the answer.
- **Announcing instead of saying.** "Let's dive in." "Let's explore." "In this article, we'll look at." "Here's the thing." "Here's what you need to know." Start with the content.
- **The colon reveal and the question reveal.** "The result? A 40% speedup." "The secret: caching." Write the sentence: "Caching made it 40% faster."
- **Cinematic setups.** "And then everything changed." "That's when it clicked." "What happened next surprised me." Say what changed.
- **Fragments for drama.** "Three hours. One line. Fixed." Write complete sentences.
- **One-sentence paragraphs for emphasis,** paragraph after paragraph. Develop the point in a real paragraph.
- **The summary ending.** "In conclusion", "In summary", "To sum up", "At the end of the day", followed by everything the reader just read. End with what changed, what remains, or an open question.
- **The engagement ending.** "What do you think? Let me know in the comments!" "Happy coding!" End when the content ends.
- **Uniform paragraphs.** Every paragraph the same length, each opening with a topic sentence and closing with a neat restatement. Vary them to fit what each one says.
- **Throat-clearing intros.** A paragraph about how important or common the topic is before the topic starts. Cut it and begin with the second paragraph.

## 3. Filler and hedging

- **Filler phrases.** "It's important to note that", "It's worth mentioning that", "It goes without saying", "Needless to say", "At its core", "When it comes to", "In terms of", "The fact that". Delete them and read the sentence again. It almost always survives.
- **Empty intensifiers.** "Very", "really", "incredibly", "extremely", "truly", "absolutely", "literally", "actually", "basically", "essentially". Cut, or replace with the number or fact that shows the degree.
- **Stacked hedges.** "This may potentially help to somewhat reduce". One hedge, where the doubt is real: "This probably reduces". In reference and how-to, no hedge: state the fact or the limit.
- **Hedging everything equally.** If every claim says "might" or "can", the reader cannot tell which ones you are sure of. Be certain where you are certain.
- **False balance.** Listing pros and cons with no view, in a mode that allows one. In explanation and narrative, say which way the trade-off falls and why.

## 4. Tone

- **Hype and announcement voice.** "We're thrilled to announce", "I'm excited to share", "Introducing". Say what it is.
- **Self-praise and effort.** "After countless hours", "I'm proud to say", "This was a huge win". Describe the work and let the reader judge it.
- **Manufactured wonder.** Presenting ordinary engineering as astonishing. A cache key fix is not a revelation.
- **Flattering the reader.** "As a savvy developer, you know." "Great question." Talk to the reader as an equal.
- **Motivational endings.** "Now go build something amazing." Cut.
- **AI as the subject.** "I asked ChatGPT", "with the help of AI", when the tool is not the topic. Write about the work.
- **Exclamation marks** used to create excitement. **Voice can allow** one where the author would genuinely say it that way.

## 5. Formatting

- **Bold scattered through paragraphs.** Bold a term where it is defined, or an interface label. Do not bold phrases for emphasis every few lines.
- **Bullets where prose belongs.** If the items need "because" or "so" to connect, write a paragraph.
- **Headings every two paragraphs.** Use a heading when the subject changes, not to break up text.
- **Emoji in headings or as bullet markers.**
- **Title Case For Every Heading.** Use sentence case.
- **A table for two items,** or a table that is really a list.
- **A "Key takeaways" box** that repeats the article. If a summary is needed, it goes at the top (a TL;DR), and it says something the reader learns.
- **Em dashes.** Models use them far more than most writers do, often to bolt a second thought onto a sentence. Use a comma, a colon, parentheses, or a new sentence. **Voice can allow** them if the author's voice file says so; even then, use them where the author would, not as a rhythm device.
- **Semicolons as a mannerism.** **Voice can allow** them.

## 6. Content

- **Vague claims.** "This can cause issues." "Performance improved significantly." Say which issue, and by how much.
- **Numbers with no method.** "3x faster" says nothing until you say on what, measured how, over how many runs.
- **Invented examples presented as real.** "One team I worked with saw a 50% drop." If it did not happen, do not write it as if it did. Label hypothetical examples as hypothetical.
- **Generic best practice.** "Write tests." "Keep functions small." The reader knows. Write what is specific to this case.
- **Restating the docs.** If the official documentation already says it, link it and add what the docs do not say.
- **Changelog as article.** "Added X. Added Y. Added Z." With no decision or reasoning, it is a list, not a piece of writing.
- **Speculative futures as plans.** "This will revolutionize how teams ship." Say what it does now.

## 7. Over-correction

Removing slop can leave text that is technically clean and still reads like a machine: every sentence short, the same length, nothing specific, no opinion, no person behind it. This is a failure too.

- Mix short and long sentences.
- Keep the author's view in explanation and narrative.
- Keep specific details, even small ones. They are what make text sound like someone who was there.
- Keep the author's natural phrasing from the voice file, as long as it is not on this list.
