# Rewrite Safety

## Default Stance

History rewriting is useful, but it is never the silent default.

The skill should be local-first and conservative:

- prefer rewriting recent local commits over anything already likely to be shared
- pause before every action that changes existing commit objects
- avoid assuming remote rewrite or force-push is acceptable

## Mandatory Confirmation Gate

Before executing any rewrite, ask for explicit confirmation.

This includes:

- `git commit --amend`
- squash
- reword
- reset
- dropping or restoring files from an existing commit
- regrouping or reordering recent local commits

Good confirmation wording is short and concrete. Example:

`I recommend squashing the last two local commits and replacing their messages with one clearer commit. This rewrites existing local history. Do you want me to proceed?`

## Shared-History Caution

Treat a rewrite as potentially risky if:

- the branch may already be pushed
- other people may have pulled the branch
- the user did not specify that the history is local and unshared

In those cases, explain the risk plainly and ask before doing anything destructive or confusing.

## Safe Defaults By Scenario

### Current working tree is messy

Preferred action:

- inspect diffs
- propose staging groups
- create new clean commits

Do not jump straight to amend or reset unless the user wants history cleanup specifically.

### Last local commit contains an accidental file

Preferred action:

- explain that removing the file from the existing commit rewrites history
- ask for confirmation
- only then perform the rewrite

### Last few commits are noisy but local

Preferred action:

- recommend squash or reword if it would produce a cleaner project story
- state that this changes existing commits
- wait for approval

## What Not To Do

- do not rewrite first and explain after
- do not assume force-push is acceptable
- do not use vague warnings like "this may change some things"
- do not treat a pushed branch the same way as private local work

## Practical Heuristic

If the operation would change commit hashes, stop and confirm first.
