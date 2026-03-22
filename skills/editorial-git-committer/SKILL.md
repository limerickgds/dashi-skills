---
name: editorial-git-committer
description: Use when users want to commit changes, improve a commit message, split mixed changes into logical commits, clean up recent local history, remove accidentally committed files, squash or reword recent local commits, or generally sort out a local Git mess before review or a PR.
---

# Editorial Git Committer

## Overview

Use this skill to treat Git history as an intentionally authored project narrative, not just a raw log of whatever happened in the terminal.

The goal is to help the user end up with:

- clearer commit boundaries
- stronger commit messages
- cleaner recent local history
- safer handling of history rewrites

## When to Use

Use this skill when the user asks to:

- commit current work
- write or improve a commit message
- split mixed changes into multiple commits
- review recent local history before a PR
- remove an accidental file from a recent commit
- squash, reword, or regroup recent local commits
- "sort out this git mess" when the mess is primarily local history or staging shape

Do not use this skill for full release workflows or remote branch management. Use a release-specific workflow for those.

## Core Rule

Do not start by writing a polished commit message.

First inspect the current state and decide whether the right answer is:

- one commit
- several commits
- or a local history cleanup

If the change boundaries are wrong, fix the shape before polishing the story.

## Operating Modes

### Mode A: Commit Current Work

Use when the work is already one coherent unit.

### Mode B: Split Mixed Work

Use when the working tree contains multiple intentions that should become separate commits.

### Mode C: Curate Recent Local History

Use when the latest local commits would tell a better story if they were reworded, squashed, regrouped, or cleaned up.

## Workflow

### 1. Inspect before authoring

Check the state first:

- `git status`
- staged diff
- unstaged diff
- recent local commits when relevant

### 2. Classify the history shape

Decide whether the work should become:

- one coherent commit
- multiple logical commits
- a rewrite of recent local history

### 3. Group by intention

When splitting work, group by meaning rather than by file count. Typical boundaries include:

- feature work
- bug fix
- refactor
- cleanup
- tests
- generated files or lockfile updates

If one commit would hide multiple intentions, say so clearly and propose a split.

### 4. Author the narrative

Draft commit messages that help a future reader understand:

- what this unit of change is
- why it exists
- how it moves the project forward

Follow repository conventions if they are visible. If not, use concise imperative phrasing.

### 5. Gate every rewrite

Before any action that rewrites existing commits, stop and ask for explicit confirmation.

Always pause before:

- `--amend`
- squash
- reword
- reset
- removing files from an existing commit
- regrouping existing commits

## Output Shape

Default to this structure:

1. current state assessment
2. recommended history shape
3. proposed commit message or messages
4. explicit confirmation gate if rewrite is required

If the user wants advice only, stop after the recommendation.
If the user wants action, execute only the safe approved local steps.

## Commit Message Principles

- Explain intent, not just filenames.
- Prefer one meaningful unit per commit.
- Do not use message polish to hide mixed work.
- Use history as a readable interface for future humans and agents.
- Stay concise unless the repository clearly prefers more detail.

## Safety Boundaries

- Default to local history, not remote surgery.
- Do not assume force-push is acceptable.
- Treat shared history as unsafe to rewrite unless explicitly confirmed.
- If the real problem is messy staging, say that before proposing message tweaks.

## References

Read the relevant supporting file when you need more depth:

- `references/editorial-history.md` for the narrative framing and commit-message philosophy
- `references/rewrite-safety.md` for rewrite decision rules and confirmation guidance
- `references/examples.md` for representative prompts and response patterns
