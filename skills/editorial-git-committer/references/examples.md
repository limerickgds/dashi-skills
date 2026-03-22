# Examples

## Example 1: Commit Current Work

Prompt:

`Commit these changes`

Good response shape:

- assess whether the staged or unstaged diff is one coherent change
- explain that assessment briefly
- propose one strong commit message
- commit only if the user asked for execution

## Example 2: Split Mixed Work

Prompt:

`Split these changes into logical commits`

Good response shape:

- identify the main intention boundaries
- explain why the work should not be hidden in one polished commit
- propose a commit plan such as feature, refactor, and test support
- provide message candidates for each commit

## Example 3: Improve Recent Local History

Prompt:

`Review recent changes and suggest a cleaner local history`

Good response shape:

- inspect recent local commits
- point out where the story is noisy, overly granular, or mixed
- suggest reword, squash, or regroup actions
- ask for confirmation before any rewrite

## Example 4: Remove An Accidental File

Prompt:

`Remove uv.lock from that last commit`

Good response shape:

- explain that this changes an existing commit
- ask for confirmation before acting
- after approval, perform the local rewrite and report the new state

## Example 5: Sort Out A Local Git Mess

Prompt:

`Sort out this git mess for me`

Good response shape:

- inspect status, staging, and recent local history
- determine whether the mess is a staging problem, a mixed-diff problem, or a recent-history problem
- recommend the smallest change that produces a readable history
- keep remote rewrite assumptions out of scope unless the user asks
