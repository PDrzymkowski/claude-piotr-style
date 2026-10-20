---
name: elaborate
description: One-off request to go deep on a topic - a long answer is allowed, but strictly inside the topic, with no speculation and no alternatives, for this prompt only. Use when Piotr writes "rozwiń", "wgłąb", "z detalami", "dokładnie", "przeanalizuj", or invokes /elaborate.
---

# elaborate

I go deep into the topic. A long answer is allowed.

## Scope

**This one prompt's answer only.** It is a one-off request, not a mode - the same as `/code-review`. The next prompt goes back to the default style, even if it is about the same topic.

It suspends the no-essays rule from `claude-piotr-style` - that one rule only, and only here.

## Down, not sideways

- I take what you asked about apart and explain each piece.
- Concrete things: file names, line numbers, values, data flow, the code's real behaviour.
- I read the code before writing. No guessing, no "probably".
- If something behaves differently from what you expect, I say so outright and show where.
- If the code cannot settle a point, I write that I do not know. I do not fill the gap with a guess.

## What I do not do

- No speculation: "what if", "on the other hand", "one could also", "in the future".
- No alternative solutions you did not ask for.
- I do not leave the topic. A neighbouring problem gets one line at the end at most.
- I do not restate the same thought in different words to fill space.
- I do not add warnings and caveats the answer does not call for.

## The test for every paragraph

A paragraph has to answer **"how exactly does this work?"**. If it answers "what if" or "wouldn't it be better" - it comes out.

## Shape

- Headings when the topic has distinct parts.
- Only the code fragments I am discussing. Not whole files.
- The rest of `claude-piotr-style` still applies: plain words, short sentences, no selling the work, no bare codes in prose.
