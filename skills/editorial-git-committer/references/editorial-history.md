# Editorial History

## Core Framing

Git history does not need to be treated as an immutable ledger of every accidental step that happened during implementation.

For local work, it is often more useful to treat history as a deliberately authored project narrative. A good history helps future humans and agents answer:

- what changed here
- why was this grouped together
- what was the intended step in the project
- where should I look if I need to review, debug, revert, or extend this work

Coding agents are unusually good at this editorial layer because they can quickly inspect diffs, compare nearby commits, notice mixed intent, and propose cleaner commit boundaries.

## What Makes A Good Commit Unit

A good commit is usually:

- coherent
- intention-centered
- reviewable
- reversible
- easy to describe in one sentence

Signals that a commit boundary is probably good:

- the change can be summarized without listing many unrelated actions
- the tests or validation connected to that change make sense together
- a reviewer could discuss this unit on its own
- reverting it would remove one meaningful step instead of half of several different ideas

Signals that a commit is probably too mixed:

- the message needs "and" more than once
- it combines feature work with cleanup or formatting
- it mixes refactoring with behavior change
- it includes generated files that distract from the main intent
- it includes a lockfile or incidental artifact that deserves separate handling

## Commit Message Philosophy

Commit messages should explain meaning, not just inventory.

Weak messages tend to:

- list touched files
- describe implementation trivia
- hide mixed intent behind vague wording
- overstate coherence that the diff does not actually have

Stronger messages tend to:

- name the change as a project step
- tell the future reader why this unit exists
- inherit the repository's established style when visible

If repository style is unclear, prefer concise imperative phrasing that focuses on intent.

## Editorial Actions The Agent Should Consider

Depending on the state of the work, the best editorial move may be:

- commit the current work as one unit
- split the work into multiple commits
- rewrite a recent message
- squash nearby commits that only make sense together
- remove an accidental file from a recent commit
- leave the history alone and just explain why it is already good enough

The agent should not assume that every diff must become one commit, and it should not assume that every messy history must be rewritten. The goal is better narrative quality, not maximal Git surgery.

## Practical Rule

When the boundaries are wrong, fix the boundaries before polishing the prose.

Do not use a clever commit message to disguise a commit that should have been split.
