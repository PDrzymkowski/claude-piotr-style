# piotr-code-style

Rules for writing code. Text inside code - docstrings, comments, commit messages - is covered by `claude-piotr-style.md`. I do not repeat it here.

## Docstrings

A function docstring has four parts, each one short sentence:

1. What the function does - one line.
2. `Args:` - a sentence per parameter.
3. `Returns:` - what comes back. `None` if nothing does.
4. `Raises:` - a sentence per exception the function can let out.

Nothing else. Forbidden:

- "X rather than Y", "X instead of Y" - that is, why this approach and not another,
- why the code is shaped the way it is,
- what would happen with a different solution,
- dramatising the consequences ("the only thing standing between ... and ...").

Exception only when Piotr explicitly asks for context in that specific spot.

Class and module docstrings follow the same rule: they describe what the thing is, not how it came to be.

## Before I write a function

- I check whether one already exists. Especially for reading and writing a model - before writing my own write, I look in the service layer.
- I pick the layer before writing, not after. Side-effect-free logic goes into the model.

## Structure

- No private function with a single-line body. I call the thing directly where it is needed.
- A function returns a model, not a `dict`.
- I build for today's requirement. Three booleans beat one universal mechanism.
- I do not save a cache read at the cost of the signature. A simpler parameter set is worth one query.
- I do not add concurrency, workers or batching until it is known they are needed.

## Names

- No empty suffixes: not `_now`, not `_json`, not `automatic_`. If the addition distinguishes nothing, it goes.
- The ordinary word over the rarer one: `normalize`, not `canonicalise`.
- I do not shadow built-in names (`type`, `id`, `list`).
- A function name matches the name of the task or job that runs it.

## Values

- A number someone may want to change without a deploy goes into settings.
- Defaults cautious, not aggressive. A timeout should wait rather than cut.

## After a change

- Removing something means walking the whole chain: export, import, docstring, variable, test, index. Not just the file I was sitting in.
- After a run of review fixes, a separate pass: I check the layers and the return types. Not alongside the last fix.

## Commits

- A commit message is the subject line and the attribution line. Nothing else, no body.
- Subject in the imperative, capitalised, no full stop, under roughly 70 characters after the prefix.
- The subject says what the change makes the code do, in the project's own words, not the names of the files it touches. "Stop acking worker tasks when Redis cannot answer the lock", not "Update worker.py".
- Cosmetics - docstring, `@define`, formatting - fold into the commit that introduced that line.
- A behaviour change gets its own commit on top.
- A commit does not promise more than it actually does.

## Tests

- A test that still passes after the thing under test is cut out is a test to throw away.
- I do not write a test for a function that decides nothing.

## Concurrency

- A function holding a lock reads its own data itself, inside the lock. No objects passed in as parameters, none read before the lock was taken.
- Every write to a document that has a lock goes under that lock.

## Tools

- I do not run Playwright on my own initiative. Only when you ask outright - even when the change touches the UI and looks worth checking in a browser.
- The same goes for skills that drive a browser underneath. I do not invoke those myself.
- If I think a look in the browser is worth it, I say so in one line and wait.

## Project-specific rules

Rules that hold for one repo only live in that repo's `CLAUDE.local.md`. There, not here and not in an instructions file the whole team shares.
