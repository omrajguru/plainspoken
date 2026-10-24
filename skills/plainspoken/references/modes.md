# Modes

Pick the mode before writing anything. One document has one mode, and the mode decides how strict the clarity rules are, whether opinion belongs in the text, and how much of the author's voice comes through.

The first four modes come from the Diátaxis framework for documentation. The fifth, **narrative**, covers the writing that most blog posts actually are: an account of a problem, a decision, or a piece of work.

## Picking the mode

Ask two questions about the material:

1. Does it help the reader **do** something, or **understand** something?
2. Does the reader come to it to **learn**, or to **get work done**?

| | Learning | Getting work done |
| --- | --- | --- |
| **Doing** | Tutorial | How-to |
| **Understanding** | Explanation | Reference |

Then ask a third: is it the account of something that happened, told so others can learn from it? If so, it is **narrative**.

Common requests and their usual mode:

| The request | Usual mode |
| --- | --- |
| "Build X with Y", "Getting started with X" | Tutorial |
| "How to do X", a troubleshooting page, a recipe | How-to |
| API docs, a config options page, a CLI reference, most of a README's usage section | Reference |
| "What is X", "Why we chose X", "How X works under the hood", an opinion piece | Explanation |
| "How I fixed X", a dev note, a case study, a postmortem, a project write-up | Narrative |

A README usually holds several modes. Keep each section in one mode and order them: what it is (explanation, a few lines), install and quick start (tutorial), usage (how-to or reference).

## How strict each mode is

| Mode | Clarity rules | Opinion | Hedges | Voice file applies |
| --- | --- | --- | --- | --- |
| Tutorial | Strict in steps, relaxed between them | No | No | Partly: person, spelling, punctuation, formality |
| How-to | Strict | No | No | Partly: spelling, punctuation |
| Reference | Strict | No | No | Only spelling and punctuation |
| Explanation | Relaxed | Yes | Where the doubt is real | Fully |
| Narrative | Relaxed | Yes | Where the doubt is real | Fully |

"Relaxed" means the rules in `references/clarity.md` marked **relaxed in explanation and narrative** may bend for rhythm and voice. Everything else in that file still applies, and the slop catalog always applies.

## Tutorial: learning by doing

The reader is learning, and their success is your responsibility.

- Open with what the reader will make, not what they will "learn".
- Every step produces a visible result, early and often. Say what they should see: the output, the page, the log line.
- Keep explanation to a clause and a link. The tutorial is not the place to teach theory.
- Stay concrete. One path, no choices, no alternatives.
- Write steps as commands. "We" is fine in tutorials: "First, we create the project."

## How-to: steps to a goal

The reader is competent and has a specific problem.

- Name the guide by the task: "How to rotate an API key", not "API key rotation".
- Solve the reader's problem, not an operation the software happens to support.
- Action only. Link background instead of including it.
- Allow forks where real work has them: "If you use Docker, do this instead."
- Start each step with the condition, then the action.

## Reference: facts for lookup

The reader wants a fact and will leave once they have it.

- Describe only. No instruction, no persuasion, no opinion.
- Be complete and certain. State options, defaults, limits, and errors without hedging.
- Mirror the structure of the thing described, so the reader can move between the code and the docs.
- Keep the same pattern for every entry: name, type, default, description, example.
- Generate from code where possible, so the reference cannot drift.

## Explanation: understanding and why

The reader wants to understand something, often away from the keyboard.

- One bounded topic. The title should still make sense with "About" in front of it.
- Start from a real "why" question, and answer it early.
- Give context: the design decisions, history, constraints, and alternatives.
- Have a view. Weigh the trade-offs and say what you make of them, rather than listing pros and cons and leaving the reader to do the work.
- Opinion is welcome, but present it as reasoning the reader can examine, not a conclusion they must accept.

## Narrative: what happened and what it taught

The reader was not there and wants to learn from what happened. Dev notes, case studies, postmortems, and project write-ups are narrative.

- Lead with the point: what the problem was and what the result was. Do not save the result for the end.
- Organise around the problem and the decisions, not the timeline. The reader does not need every step in order.
- For each technical part, cover: what the problem was, what was actually happening, why it was happening, what changed, and what effect the change had.
- Include the dead ends when they teach something. An approach that failed often explains the final one better than the final one does.
- Keep ordinary engineering ordinary. A cache key fix is a cache key fix, not a discovery.
- End with what changed, what remains, or the open question the work raised. Do not end with a summary of the whole piece.

A narrative piece may include a short code snippet or a fix the reader can copy. If it grows into a full set of steps, move the steps into a separate how-to and link it.

## Do not mix modes

- No reference tables inside a tutorial.
- No hand-holding inside reference.
- No arguing inside a how-to.
- No step-by-step procedure in the middle of an explanation.

When the material needs two modes, split it into two documents or two clearly separate sections, and link them.
