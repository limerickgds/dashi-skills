# PNG Review Checklist

Do not stop at “the diagram exists.” Check whether it is actually ready to show someone.

## 1. Start with structure

Before pixel-level polish, answer:

1. Is the main reading path obvious?
2. Does the visual structure match the conceptual structure?
3. Do the most important ideas occupy the most visually important positions?
4. If the text disappeared, would the structure still resemble the intended flow, architecture, or sequence?

If the answer is no, fix structure first.

## 2. Connection checks

### High priority

- arrow connects to the wrong element
- arrow endpoint lands in empty space
- branch label does not match the branch
- arrow crosses through an important container and changes the meaning

### Medium priority

- too many arrow crossings
- primary flow and exception flow are not visually differentiated
- labels are too far from the line they describe

### Low priority

- routing bends are sloppy
- spacing between parallel arrows is inconsistent

## 3. Text checks

- is the title visually strong enough?
- is there a clear hierarchy between section headers and node labels?
- is the body text readable?
- is any text clipped?
- does a long label distort the node too much?
- are technical terms preserved correctly?

## 4. Layout checks

- are elements overlapping unnecessarily?
- is the composition obviously left-heavy, right-heavy, top-heavy, or bottom-heavy?
- does excess empty space break the reading path?
- do important nodes have enough breathing room?
- do background regions clarify the structure instead of competing with it?

## 5. Diagram-type fit

Check whether the wrong visual mode was chosen:

- something that should be a flowchart became a row of generic relation cards
- something that should be a sequence diagram lacks a clear time direction
- something that should be an architecture diagram has nodes but no boundaries or layers
- something that should be a mind map does not radiate from a central topic
- something that should show branching or convergence is just a linear chain of rectangles

If the type is wrong, fix the structure before polishing.

## 6. Technical-diagram checks

- are real event names, API names, field names, or module names present where needed?
- do evidence blocks actually teach something?
- are evidence blocks oversized relative to the main flow?
- are data flow and control flow being confused?
- are storage, cache, queue, and service roles visually distinguished?

## 7. Revision priority

Fix in this order:

1. structural errors
2. connection errors
3. readability problems
4. layout balance
5. visual polish

Do not reverse that order.

## 8. Stop condition

You can stop when:

- the main path is clear
- key relationships are correct
- there is no obvious clipping or overlap
- technical and non-technical text are both readable
- the chosen diagram type matches the content
- the remaining differences are mostly preference, not quality defects
