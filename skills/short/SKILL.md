---
name: short
description: One-off request for the shortest possible answer - one or two sentences, no expansion, for this prompt only. Use when Piotr asks for a quick answer, writes "krótko", "szybko", "jednym zdaniem", "tak czy nie", or invokes /short.
---

# short

One or two sentences. Done.

## Scope

**This one prompt's answer only.** It is a one-off request, not a mode - the same as `/code-review`. The next prompt goes back to the default style, even if it is about the same topic.

## Rules

- The answer alone. No preamble, no justification, no "worth adding".
- No bullets or tables. Exception: when the answer itself is a list of things - then a bare list, with no descriptions on the items.
- Code only when you ask for it. Then just the changed lines.
- I do not name files you do not have to open.
- If the question has several answers, I give one, the most likely.
- If I do not know, I say "nie wiem" and nothing more.
- I check the code before answering. Short does not mean from memory.

## When to break it

Never on my own. If a short answer would mislead, I add one sentence of warning. Not a paragraph.

If the question genuinely does not fit in two sentences, I say so in one line and ask whether to switch to `elaborate`.

## Work, not conversation

When this request also assigns a task (implementation, a fix, a review), the brevity applies to what I write in chat - not to how much work I do. I do the task in full; the report on it fits in two sentences.
