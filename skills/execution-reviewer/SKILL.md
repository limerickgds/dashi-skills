---
name: execution-reviewer
description: Reviews the execution history after a task is completed and turns it into a concise retrospective, handoff, or improvement memo. Use this whenever a coding, writing, research, planning, debugging, or operational task has just finished; whenever files, commands, tests, or deliverables were produced; whenever the user asks to summarize what was done, review the execution, create a handoff, capture lessons learned, or prepare for the next iteration; and preferably before commit, release, or transfer to another agent. If there is execution evidence in the conversation, err on the side of using this skill instead of waiting for the user to ask explicitly.
---

# Execution Reviewer

## Purpose

Turn a finished piece of work into a useful review that helps the user understand:

- what was supposed to happen
- what actually happened
- what evidence supports that summary
- what changed along the way
- what should happen next

This skill is for execution review, not abstract reflection. Focus on the work history, decisions, artifacts, outcomes, and follow-up actions.

## When to use

Use this skill when the task has meaningful execution history, such as:

- code changes, file edits, or generated assets
- commands run in a shell
- tests, builds, lint checks, or deploy attempts
- research steps with sources gathered and conclusions reached
- planning or writing tasks that produced drafts, outlines, or final documents
- multi-step agent work that the user may want summarized or handed off
- multi-turn or cross-agent work where ownership boundaries matter for continuation

Good trigger phrases include:

- "review what you just did"
- "summarize the execution"
- "give me a handoff"
- "what happened in this task?"
- "复盘一下这次执行"
- "总结刚才做了什么"
- "把这次任务的过程整理一下"

## Core principles

### 1. Be evidence-based

Only summarize what is supported by the available history: user instructions, plans, commands, outputs, file changes, tests, and final results.

If something is uncertain, label it as an inference.

### 2. Lead with outcome

Users usually want to know whether the task succeeded before they want the full story. State the result first, then explain how the work got there.

### 3. Be constructive, not defensive

A review should help the next step happen faster. Surface misses, risks, and detours without sounding apologetic or self-congratulatory.

### 4. Preserve decision context

When the execution involved tradeoffs, capture why a path was chosen. This is often more valuable than the raw action list.

### 5. Always end with momentum

Every review should end with the clearest next action, even if the next action is simply "nothing more needed."

### 6. Preserve ownership boundaries when they matter

If multiple agents, people, or turns contributed to the result, keep the handoff-relevant ownership boundaries intact. The next reader should be able to tell which work is already complete, which actor stopped where, and what does not need to be repeated.

## Review workflow

### Step 1: Reconstruct the task frame

Identify:

- the user's requested goal
- any important constraints or preferences
- the definition of done, if visible

If the original goal shifted during execution, note both the initial goal and the final working goal.

### Step 2: Gather execution evidence

Look through the available history and collect the important signals:

- plan steps and status changes
- commands executed and their outcomes
- files created, modified, or proposed
- tests or validations run, including failures
- notable intermediate decisions or pivots
- which agent, turn, or owner performed a key step when that affects continuation

Prefer a few high-signal facts over an exhaustive event dump. If the history is noisy, keep only the 3-7 transitions that materially changed direction, validation status, or delivery risk. Ignore cosmetic edits unless they changed the outcome.

### Step 3: Compare intent vs result

Answer these questions clearly:

- Was the task completed, partially completed, blocked, or intentionally deferred?
- What tangible outputs exist now?
- What parts changed from the original plan?

### Step 4: Extract reusable insight

Identify what the history suggests about future work:

- repeated friction points
- assumptions that proved right or wrong
- steps that should be standardized next time
- risks that still need watching

### Step 5: Recommend the next move

Close with a practical next action. When possible, give one recommended next move rather than a vague menu.

## Review modes

Choose the lightest mode that matches the task.

### Mode A: Quick Review

Use for small tasks or routine completions.

Keep it short and focused on:

- result
- key actions
- current status
- next step

### Mode B: Deep Review

Use for longer or more complex work such as debugging sessions, refactors, releases, migrations, or multi-turn agent execution.

Include:

- goal vs result
- concise execution timeline
- key decisions and tradeoffs
- artifacts and validation
- unresolved risks
- lessons for the next iteration

### Mode C: Handoff Review

Use when the output is meant for another human or agent to continue.

Prioritize:

- current state
- who completed which meaningful part, when that matters
- what changed
- what still needs doing
- the exact files, commands, or checks the next person should look at

## Output format

Choose one of the templates below.

### Quick Review template

```markdown
## Execution Review

### Outcome
- [What was completed and current status]

### Key Actions
- [Most important action]
- [Most important action]

### Evidence
- [Files changed, commands run, tests, or outputs]

### Risks or Gaps
- [Anything incomplete, uncertain, or unverified]

### Recommended Next Step
- [Single best next move]
```

### Deep Review template

```markdown
## Execution Review

### Goal vs Result
- Goal: [Original requested outcome]
- Result: [What now exists]
- Status: [Completed / Partial / Blocked / Deferred]

### Execution Timeline
- [Step 1]
- [Step 2]
- [Step 3]

### Key Decisions
- [Decision and why it was made]

### Artifacts and Validation
- [Files changed or created]
- [Commands, tests, builds, or checks]

### Deviations and Open Risks
- [What differed from plan or remains unresolved]

### Reusable Lessons
- [What should be repeated or avoided next time]

### Recommended Next Step
- [Single best next move]
```

### Handoff Review template

```markdown
## Handoff Review

### Current State
- [What is done]
- [What is not done]

### What Changed
- [Important modifications or decisions]

### Evidence to Inspect
- [Key files, commands, outputs, or tests]

### Open Questions
- [Questions the next person must answer]

### Recommended Next Step
- [Best immediate continuation]
```

If multiple agents were involved, name the actor only on the bullets where ownership changes the continuation plan. Do not turn the handoff into a full transcript.

## Handling incomplete history

If the execution history is partial:

- summarize only what is clearly visible
- explicitly list missing evidence
- avoid pretending to know exact steps that were not captured

Use phrasing like:

- "Visible in the history: ..."
- "Not confirmed from the available record: ..."
- "Likely inference, not directly shown: ..."

## Handling cross-agent history

If multiple agents or people touched the task:

- merge the work into one coherent story, but keep actor boundaries where they affect handoff or trust
- prefer actor labels for high-signal transitions, not every bullet
- make blockers ownership-aware: say who got blocked and on what exact step
- distinguish carefully between "prepared locally" and "completed externally" for release, deploy, or publish workflows

Good phrasing includes:

- "Planner agent defined the sequence, then Executor agent completed the local edits."
- "Release preparation is complete locally, but external publishing is still blocked."
- "The next agent should resume from the blocked release step rather than repeating earlier prep work."

## Tone guidelines

- Be clear and calm.
- Be concise unless the task clearly needs a deep review.
- Do not overpraise routine work.
- Do not bury risks under positive language.
- Do not turn the review into a blame exercise.

The best review feels like a sharp project note written by a reliable chief of staff.

## Example 1

Input: "复盘一下刚才这个修 bug 的过程，给我一个可以发给同事的总结。"

Output:

```markdown
## Handoff Review

### Current State
- Fixed the null-handling path in the parser and updated the related unit test.
- The regression case is covered, but full integration coverage was not rerun.

### What Changed
- Adjusted the parser fallback logic to return a safe default instead of throwing.
- Added a focused test for empty payload input.

### Evidence to Inspect
- `src/parser.ts`
- `tests/parser.test.ts`
- Focused unit test output for the parser suite

### Open Questions
- Does the same null-handling issue exist in the streaming parser path?

### Recommended Next Step
- Run the adjacent parser integration tests before merging.
```

## Example 2

Input: "总结一下你刚刚做的调研工作，顺便说说下一步建议。"

Output:

```markdown
## Execution Review

### Outcome
- Compared three implementation approaches and identified one recommendation with lower migration risk.

### Key Actions
- Gathered the existing constraints from the repo and task history.
- Compared the options against maintenance cost and rollout complexity.

### Evidence
- Notes from the current conversation and the documented constraints.

### Risks or Gaps
- The recommendation is not yet validated against real production traffic.

### Recommended Next Step
- Prototype the recommended approach on the smallest non-critical path first.
```

## Example 3

Input: "把这次跨 agent 的发布准备交接给下一位 agent。"

Output:

```markdown
## Handoff Review

### Current State
- Release preparation is complete locally: changelog and version were updated, build artifacts were generated, and the blocking test issue was fixed.
- External publishing is still not complete because the production release token was unavailable.

### What Changed
- Planner agent defined the release sequence.
- Executor agent completed the local release-prep changes.
- Test-fixer agent refreshed the failing fixture and reran the tests successfully.
- Release agent stopped at the publish step because credentials were missing.

### Evidence to Inspect
- `CHANGELOG.md`
- `package.json`
- Passing test output
- Release logs showing missing credentials

### Open Questions
- Is the production release token now available to the next agent?

### Recommended Next Step
- Re-enter at the blocked publish step instead of repeating earlier release-prep work.
```

## Final reminder

This skill is useful precisely because execution history is easy to lose. When a meaningful task has just ended, prefer writing the review now while the evidence is still fresh.
