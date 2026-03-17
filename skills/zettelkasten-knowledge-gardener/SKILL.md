---
name: zettelkasten-knowledge-gardener
description: A Zettelkasten-based knowledge gardening skill. Use this whenever users want to organize a knowledge base, 整理知识库, 整理读书笔记, build a second brain, update a personal wiki, turn conversations, reading notes, or project learnings into evergreen notes, MOCs, PARA folders, reusable context packs, or long-term memory assets. Trigger even when the user only says their notes are scattered, duplicated, stale, or hard to reuse.
---

# Zettelkasten Knowledge Gardener

## Theory Base

This skill combines five compatible ideas:

- **Zettelkasten**: keep notes atomic, linked, and composable instead of storing large undifferentiated documents
- **How to Take Smart Notes**: move from capture -> literature notes -> durable notes
- **Evergreen notes**: write notes as living ideas that can be revised and reused
- **PARA**: organize the garden by action context: Projects, Areas, Resources, Archives
- **Progressive Summarization**: keep useful compression layers so future retrieval is fast

Use the theory as a practical system, not as ideology. The goal is not to imitate a perfect note-taking religion. The goal is to help the user build a knowledge garden that stays useful over time.

## Purpose

Turn messy material such as:

- conversations
- reading notes
- research fragments
- project lessons
- personal wiki pages
- saved links and highlights

into reusable knowledge assets such as:

- atomic notes
- evergreen notes
- MOC or index pages
- context packs for future prompting
- review and pruning queues

This skill is for knowledge maintenance, not just summarization. It should always leave behind artifacts that can be reused later.

## When to Use

Use this skill whenever the user wants to:

- organize or clean up a knowledge base
- turn a book, article set, or conversation log into durable notes
- create a second-brain style system
- refresh a personal wiki or notes vault
- extract reusable context from a project or research stream
- merge duplicate notes or identify stale knowledge
- prepare a prompt-ready context pack from existing notes

Strong trigger phrases include:

- "organize my knowledge base"
- "整理知识库"
- "整理读书笔记"
- "build a second brain"
- "update my personal wiki"
- "turn this into evergreen notes"
- "create an MOC"
- "make this reusable later"

## Core Principles

### 1. Prefer durable knowledge over raw storage

Do not simply archive what the user gives you. Distill what is worth keeping.

### 2. Keep notes atomic

Each note should hold one idea, one claim, one principle, one case, or one open question. Avoid packing many unrelated ideas into one note.

### 3. Separate evidence from interpretation

Every durable artifact should distinguish:

- **Facts**: what the source directly supports
- **Inferences**: what is concluded or generalized
- **Open Questions**: what is unresolved
- **Review Trigger**: what should cause the note to be revisited

### 4. Titles should help retrieval

Prefer note titles that are specific and statement-like. A good evergreen title can often be read as a claim.

Bad:
- "RAG notes"
- "Book highlights"

Better:
- "Retrieval quality degrades when chunk boundaries ignore task intent"
- "Prompt context packs should preserve source confidence, not just conclusions"

### 5. Link before filing

Do not create isolated notes if they clearly relate to existing ideas. Surface the most meaningful links and clusters.

### 6. Prune aggressively

Mark notes as stale, duplicate, contradictory, or low-value when the evidence supports that judgment.

## Operating Modes

Choose the lightest useful mode.

### Mode A: Quick Harvest

Use for one article, one conversation, or a small note batch.

Output:

- atomic notes
- 1 small index section
- short review queue

### Mode B: Reading Distillation

Use when the user finished a book, paper set, or long article cluster.

Output:

- literature notes
- evergreen notes
- concept links
- reading-derived context pack

### Mode C: Garden Refresh

Use when the user already has a note system and wants cleanup or restructuring.

Output:

- duplicate map
- stale note list
- conflict list
- PARA placement recommendations
- pruning and review plan

### Mode D: Prompt Context Pack

Use when the user wants to turn existing knowledge into something an agent can reuse immediately.

Output:

- compact background brief
- key principles
- known uncertainties
- source confidence notes
- suggested prompts or future retrieval hooks

## Knowledge Unit Model

When you create or reshape notes, use this internal model:

```markdown
## [Note Title]
Type: Fact / Principle / Case / Open Question
Source: [conversation, book, article, project, or "not specified"]

Facts
- ...

Inferences
- ...

Open Questions
- ...

Links
- [[Related note]]
- [[Related MOC]]

Review Trigger
- Revisit when ...
```

Not every user-facing output needs to show every field in full, but the skill should reason with these distinctions.

## Workflow

### Step 1: Clarify the gardening goal

Identify:

- what material the user is giving you
- whether the goal is capture, distillation, cleanup, or reuse
- whether the user wants a note system, a context pack, or both

### Step 2: Separate signal from note clutter

Break the material into units such as:

- facts
- principles
- examples
- decisions
- open questions
- repeated but low-value fragments

Do not give equal weight to everything.

### Step 3: Create atomic notes

Rewrite high-value material into reusable units. Each unit should be understandable without the entire original source sitting beside it.

### Step 4: Link and cluster

Show how the notes connect:

- parent concept -> child idea
- general principle -> concrete example
- question -> possible answer
- conflicting interpretations

When useful, create a small MOC or index page instead of only isolated notes.

### Step 5: Place into PARA

Recommend where the outputs belong:

- **Projects**: active, time-bound efforts
- **Areas**: ongoing responsibilities
- **Resources**: reference material
- **Archives**: inactive but worth preserving

Do not force PARA labels if the input is too sparse; say so clearly.

### Step 6: Add compression layers

Use progressive summarization:

- raw source or source pointer
- distilled bullets
- evergreen note
- prompt-ready context pack

This lets the same knowledge be useful at different levels of time pressure.

### Step 7: Leave maintenance hooks

Always end with at least one of:

- a pruning list
- a review queue
- conflict checks
- stale note warnings
- future retrieval hooks

## Output Format

Use this structure unless the user asks for something more specific.

```markdown
# Knowledge Garden Update

## Goal
- [What this gardening pass tried to accomplish]

## Inputs
- [Sources or material processed]

## Atomic Notes
- [Note title]: [1-2 sentence summary]

## Evergreen Notes
- [Claim-like note title]: [Why it matters]

## Links or MOC
- [Cluster, index page, or concept relationship]

## PARA Placement
- Projects:
- Areas:
- Resources:
- Archives:

## Context Pack
- Facts:
- Inferences:
- Open Questions:
- Review Triggers:

## Pruning or Review Queue
- [Duplicate, stale, contradictory, or follow-up item]
```

If the user wants a lighter output, compress the same logic rather than dropping the distinctions.

## Handling Messy Inputs

If the source material is weak or incomplete:

- say what is directly supported
- mark what is inferred
- do not invent links that are not justified
- explicitly note when a note is not yet evergreen quality

Useful phrases:

- "Worth capturing, but still too raw for an evergreen note."
- "Duplicate idea with lower signal than the existing note."
- "Potential link, but not well supported yet."
- "Archive unless this becomes relevant to an active project."

## Quality Bar

A strong response from this skill should:

- leave behind reusable artifacts instead of a generic summary
- preserve the line between facts and inference
- create notes that can be linked, updated, or pruned later
- recommend structure without becoming bureaucratic
- help the user's knowledge get easier to retrieve over time
