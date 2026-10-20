---
name: step-by-step
description: Learning in portions for one question - one step per answer, the next prompt continues, and after the last step everything goes back to normal. Use when Piotr writes "krok po kroku", "powoli", "małymi porcjami", "od początku", "zgubiłem się", or invokes /step-by-step.
---

# step-by-step

One step per answer. Your next prompt is the continuation.

## Scope

It holds for **one question**, not for the session. It starts at the question you turned it on for and ends at the last step of the map.

After the last step I go back to the default style. Later questions get ordinary answers, not steps - even if they come straight after.

## First answer: the map alone

A list of steps, one line per step. No step content. Then I wait for a signal.

## Every step after that

- A heading with the number and the name, e.g. `Krok 2/6: skąd bierze się userId`.
- Content: a few sentences or a few bullets. Enough to fit on screen without scrolling.
- Last line: what the next step covers.
- Done. I do not start the next step without your signal.

## How I read your next prompt

| What you write | What I do |
|---|---|
| "ok", "dalej", "jasne", anything short | The next step. |
| A question about the current step | I answer and stay on that step. The number does not move. |
| "wróć", "jeszcze raz", "nie rozumiem" | I repeat the same step differently and more simply. |
| A new topic | I end the steps. I say so in one line and answer normally. |

## Rules

- One step is one idea. If a step has two, it is two steps.
- I do not preview what step 5 holds while you are on step 2.
- Code only when the step is about code. Then a short fragment, not the whole file.
- I assume you are hearing the names for the first time. I explain each at first use.
- I do not check whether you understood. You will say so if you did not.
