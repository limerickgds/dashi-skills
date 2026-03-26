---
name: visual-knowledge-excalidraw
description: Use when users want Excalidraw diagrams, flowcharts, architecture diagrams, sequence diagrams, data-flow diagrams, mind maps, concept maps, or Obsidian `.excalidraw.md` files, especially when they want the diagram reviewed against an exported PNG and refined for layout, connections, and readability.
---

# Visual Knowledge Excalidraw

## Overview

Use this skill to create Excalidraw diagrams that are structurally meaningful rather than box-and-label layouts.

Default delivery flow:

1. Turn the content into a real visual structure
2. Produce an Obsidian-compatible `.excalidraw.md`
3. Write it to the current directory
4. If validation prerequisites are available, run the optional Obsidian PNG validation loop on the generated note
5. Inspect the exported image
6. Refine layout, connections, hierarchy, and readability

If the user explicitly wants only a draft, you may skip validation. The default deliverable is the `.excalidraw.md` note itself. When the environment can operate on that generated note, continue into the PNG validation loop; if it cannot, deliver the draft and state the blocking condition.

## When to Use

Use this skill when the user wants:

- an `Excalidraw` diagram
- a `flowchart`, `architecture diagram`, `system diagram`, or `sequence diagram`
- a `data-flow diagram`, `relationship map`, or `mind map`
- an Obsidian-native `.excalidraw.md` file
- a diagram reviewed against a PNG export and improved afterward

Do not use this skill when:

- the user explicitly wants `Mermaid`, `Canvas`, or another format
- the user only wants a text summary
- the user wants a polished UI mockup rather than a knowledge or structure diagram

## Compatibility

This skill assumes:

- file write access in the current directory

For the optional PNG validation loop, the environment must also provide:

- a reliable way to make the generated note the active Obsidian file
- `obsidian command` or equivalent automation that can export the active Excalidraw note to PNG
- `obsidian screenshot` or equivalent image capture unless the exported PNG can be read directly
- image reading / inspection capability

This repository does not bundle Obsidian automation. If those validation capabilities are not available, or if the generated note cannot be opened as the active file for export, you may still generate the `.excalidraw.md` draft, but you must clearly state that the validation loop did not run.

## First Reads

Read these files in order before working:

1. `references/color-palette.md`
2. `references/json-schema.md`
3. `references/element-templates.md` when you need concrete element structures
4. `references/obsidian-workflow.md` before writing files or attempting export validation
5. `references/optimization-checklist.md` before reviewing the PNG

## Core Philosophy

A diagram should express structure and argument, not merely place text inside containers.

Always apply these two checks:

- **Isomorphism test**: If the text disappeared, would the structure still communicate flow, branching, grouping, or convergence?
- **Teaching test**: Would a reader actually learn something from the diagram, rather than just seeing labeled boxes?

For technical diagrams:

- prefer real interface names, event names, field names, and component names
- include evidence blocks when concrete payloads, sequences, or APIs improve understanding
- avoid generic “service A -> service B” arrows with no context

## Depth Assessment

Decide the diagram depth before drawing.

### Conceptual diagrams

Use for:

- mental models
- conceptual systems
- relationship maps
- high-level workflows

Requirements:

- make the structure visually clear
- keep implementation detail light
- emphasize hierarchy, causality, grouping, and reading order

### Technical diagrams

Use for:

- system architectures
- data flows
- protocols and sequences
- engineering workflows
- tutorial-style diagrams

Requirements:

- research the real terminology first
- include relevant fields, events, or APIs
- add evidence blocks where they help
- review the rendered PNG before treating the work as done whenever the validation loop is available

## Diagram Selection

Choose one primary diagram mode:

- **Flowchart**: start, decisions, branches, outcomes
- **Sequence / timeline**: ordered events, message exchange, state progression
- **Architecture**: layers, boundaries, dependencies, data paths
- **Relationship map**: influence, dependency, collaboration, coupling
- **Mind map**: one central theme expanding outward
- **Matrix / comparison**: dimensions and contrast rather than time

Each diagram should have one dominant reading path. Do not mix incompatible reading models in the same central composition.

## Visual Patterns

Match the visual pattern to the concept:

- one-to-many: fan-out
- many-to-one: convergence
- sequential stages: timeline or chained flow
- layered system: lanes or stacked regions
- iterative improvement: loopback arrows
- decisions: diamond or visibly branching shape
- evidence: dark evidence block or callout

If every concept becomes the same card shape, the diagram is under-designed.

## Default Workflow

Unless the user explicitly asks for a draft only:

1. Understand the goal, audience, and output use case
2. Decide whether this is conceptual or technical
3. Choose the diagram type and plan reading order, major regions, and evidence blocks
4. Confirm whether the optional validation prerequisites in `references/obsidian-workflow.md` are available for the target note, including vault location, export command, and a reliable way to make the generated note the active Obsidian file
5. Generate the `.excalidraw.md` using `references/json-schema.md` and `references/element-templates.md`
6. Follow `references/obsidian-workflow.md` to write the file into the current directory
7. If the validation prerequisites are missing, or if the user asked for draft-only output, stop at draft delivery and report exactly what blocked PNG validation
8. Trigger PNG export
9. Read or capture the exported PNG
10. Review it using `references/optimization-checklist.md`
11. Revise and export again
12. Only then report completion

Default to 1-3 refinement rounds. Stop earlier only if no meaningful issues remain.

## Obsidian Output Contract

Default filename pattern:

`[topic].[diagram-type].excalidraw.md`

Use this exact wrapper structure:

````markdown
---
excalidraw-plugin: parsed
tags: [excalidraw]
excalidraw-autoexport: png
---
==⚠  Switch to EXCALIDRAW VIEW in the MORE OPTIONS menu of this document. ⚠== You can decompress Drawing data with the command palette: 'Decompress current Excalidraw file'. For more info check in plugin settings under 'Saving'

# Text Elements
%%
# Drawing
```json
{complete JSON}
```
%%
````

Key constraints:

- output `.excalidraw.md`, not a generic `.md`
- preserve the `# Text Elements` and `# Drawing` section headers exactly
- keep `excalidraw-autoexport: png` in frontmatter by default
- use the Obsidian Excalidraw plugin source, not `https://excalidraw.com`

## Text and Layout Rules

- prioritize readability over hand-drawn style
- default to `fontFamily: 2`; if the export shows missing glyphs or poor readability, switch to a more reliable font strategy
- titles should usually be `24-32px`
- primary node text should usually be `18-24px`
- body labels should not drop below `16px`
- keep at least `24px` between nearby elements and at least `48px` between major regions
- bind arrows to elements whenever possible
- route arrows around containers when a straight line creates ambiguity
- leave margin around the whole composition
- do not rely on emoji for hierarchy

## Large Diagram Rule

Do not design a large diagram as one undifferentiated surface.

Break it into sections such as:

- overview
- main flow
- supporting detail
- evidence

Get the main flow right first, then add annotations and evidence.

## Validation Rule

JSON alone is not enough to judge diagram quality.

After the first draft, review the exported PNG and check for:

- incorrect arrow targets
- arrows crossing through important elements
- clipped, tiny, or crowded text
- imbalanced composition
- fallback into generic card layouts instead of meaningful structure

If export or screenshot fails:

- do not pretend validation succeeded
- say exactly which step failed
- keep the generated `.excalidraw.md` path and provide the next best follow-up

Only promise PNG validation after confirming that Obsidian can operate on the generated note rather than some other active file.

## Final Response

Report:

- the generated `.excalidraw.md` path
- the exported PNG path
- the selected diagram type
- whether the PNG validation loop actually ran
- the most important refinements made in the last pass

## References

- `references/color-palette.md`
- `references/json-schema.md`
- `references/element-templates.md`
- `references/obsidian-workflow.md`
- `references/optimization-checklist.md`
