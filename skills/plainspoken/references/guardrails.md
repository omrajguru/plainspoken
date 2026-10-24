# Guardrails

This file holds two lists. **Approval-gated** items can appear in a piece only after the author approves each one. **Banned** items are never proposed at all.

## Approval-gated

Collect each of these on the approval list in the outline, and present the list in the approvals phase (or before the rewrite, in the quick flow). Number each item and say what it supports, so the author can answer item by item ("approve 1, 3; reject 2").

Nothing on this list reaches the draft until it is approved. A rejected item is dropped. Do not reword the text to keep a rejected claim, link, name, or quote alive.

1. **Every link.** External URLs, documentation, PRs, commits, issues, repositories, dashboards, staging or preview URLs. Give the exact URL and the sentence it supports.
2. **Related reading.** Each related article or link is approved on its own.
3. **Naming anyone.** Teammates, collaborators, clients, companies, and anyone quoted or credited.
4. **Quotes from conversations.** Chat messages, email, issue threads, review comments, and the AI session itself.
5. **Code from private repositories.** Show the snippet exactly as it would appear.
6. **Screenshots and recordings** that might show private data, file paths, email addresses, account names, or internal tools. Describe what is visible.
7. **Sensitive numbers.** Costs, billing, revenue, user counts, traffic, and anything that reveals the size of a business.
8. **Opinions about other products, tools, or companies.**
9. **Anything tagged inferred.** A conclusion drawn without evidence must be confirmed before it is written as fact.
10. **Any mention of the AI tool.** If the piece mentions it at all, it is one optional credit line, and it needs approval.

When editing a draft the author wrote, links, names, and quotes they already included are approved. Gate only what you add.

## Banned

Never propose these as a section, a topic, an aside, or a summary point. If something banned is the only interesting thing in the material, tell the author it is not worth an article.

### About the AI and the process

- Prompting as the subject: "I asked the AI to do this", or any framing where the tool is the story.
- Retelling the session in order: "first I opened the file, then I ran the tests, then".
- Tool and environment boilerplate: installing dependencies, editor setup, lint configuration. The exception is when the setup itself is the lesson.

### Low value

- Routine changes: renames, formatting, dependency bumps, typo fixes, lockfile changes, copy tweaks.
- Generic best practice the reader already knows.
- Restating official documentation without adding what it does not say.
- A changelog presented as an article.
- A feature tour with no decision or reasoning behind it.

### Integrity and safety

- Numbers without a stated method of measurement.
- Invented examples, quotes, or results presented as real.
- Secrets, API keys, tokens, environment variable values, internal hostnames, and personal data. These are banned outright, not approval-gated. Remove them from code snippets and screenshots before proposing them.
