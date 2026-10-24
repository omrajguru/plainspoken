# The grill

The grill makes sure the author understands every point before it is written. You never ask an open question and wait. You propose answers, explain each one, and recommend one. The author picks, corrects, or parks.

A point is **locked** when the author picks an option or writes their own explanation. A point is **parked** when they pick D. Parked points never reach the outline or the text.

The grill should feel like a sharp colleague checking your reasoning, not an exam. Be brisk and friendly, ask only what the evidence cannot settle, and never make the author feel slow for picking D.

## Question format

```
❓ Q<n> · <Type> · <short title>
<Context: one or two sentences grounded in evidence. Name the commit, file, PR, source, or number. If there is no evidence, say the point is inferred.>

- A) <option>: <what it means and what follows from it>
- B) <option>: <what it means and what follows from it>
- C) <option>: <what it means and what follows from it>
- D) I can't explain this yet: parks the point; it stays out of the piece.

➡️ Recommended: <letter>, because <the reason, tied to the evidence>.
```

Rules for every question:

- Three real options (A to C) plus D. Never two, never five.
- Each option is a complete, plausible answer with its consequence. No strawmen added to make the recommendation look good.
- The recommendation follows the evidence, not the most flattering reading of the work.
- At most 5 questions per message (3 in the quick flow). Group them by insight.
- The author can answer in shorthand: `1A 2C 3D`, or a letter with a correction (`2B, but only on cold starts`).
- If the author writes their own answer instead of a letter, restate it in one or two sentences and ask them to confirm before you lock it.
- Questions, options, and recommendations follow `references/slop.md` and use no em dashes, whatever the voice file says.

## How much to ask

- Ask about every insight tagged **inferred** or **needs author**.
- Ask about a **verified** insight only if it will carry a main section, and then only an explain-back question.
- For a typical article, aim for one or two messages of questions in round 1. If you need more than ten questions, the piece probably covers too much. Suggest a Scope question first.

## Question types

Use the type that fits the insight. Most main insights need one or two questions of different types.

### Explain-back

Can the author explain what was happening, in plain language, to someone who has never seen the code or the subject?

- If the cause is uncertain, the options are the competing explanations, and the recommendation names the evidence that favours one.
- If the cause is clear, the options are three framings of the same explanation: what a user saw (behaviour), what the system did (mechanism), and which code did it (implementation). Recommend the one that suits the reader in the voice file.

### Decision

Why this approach and not the alternatives?

- The options are the approach taken and the two strongest alternatives that were realistically available.
- Each option states its cost: complexity, performance, money, maintenance, or time.
- If the evidence suggests another approach would have been better, say so.

### Evidence

What shows it worked, and how was that measured? For a piece written from a topic, what source supports the claim?

- The options are the candidate measures or sources, each with its method and its weakness.
- If no measurement exists, one option must be: "Describe the effect without a number, and say it was not measured."

### Reader

What would a reader get wrong if they copied this?

- The options are the likeliest mistakes: the case where it does not apply, the precondition that is easy to miss, the edge case that broke during the work.
- The chosen option usually becomes a caveat or a gotcha in the piece.

### Honesty

Which part did the author not fully understand while doing it?

- The options are the parts most likely to be unclear: a fix that worked without a confirmed cause, a library behaviour taken on trust, a number whose method is unknown.
- The outcomes are to present it in the piece as an open question, to investigate before writing, or to cut it.

### Scope

Is this worth including at all?

- The options are a main section, a short aside or caveat, or cutting it.

## Round 2 (approvals, full flow)

After the author picks an outline, ask at most 3 questions about structure, not facts:

- Why the sections come in this order: what the reader must understand before the next section makes sense.
- What a chosen diagram or image shows that prose cannot.
- What the reader should take away from the ending.

## Example

```
❓ Q2 · Decision · Why keep filters in the URL
The search page used to keep its filters in component state (src/search/useFilters.ts before a3f91c2). The change moved them into URL parameters.

- A) URL parameters: filters survive reloads and shared links, and the back button works; the cost is encoding and decoding on every change.
- B) Component state: the simplest option, but filters are lost on reload and cannot be shared.
- C) A global store: shared across pages, but it adds a dependency and still loses state on reload unless it is persisted.
- D) I can't explain this yet: parks the point; it stays out of the piece.

➡️ Recommended: A, because the bug reports in issue 41 were about filters lost after a reload, and only A addresses that.
```
