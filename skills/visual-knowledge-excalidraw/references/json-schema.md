# Obsidian Excalidraw Structure Reference

This skill defaults to Obsidian Excalidraw plugin-compatible `.excalidraw.md` files.

## Wrapper structure

Use this exact wrapper:

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
{JSON data}
```
%%
````

Notes:

- default file extension: `.excalidraw.md`
- keep `excalidraw-autoexport: png` in frontmatter
- preserve the `# Text Elements` and `# Drawing` section headers exactly

## Root JSON object

```json
{
  "type": "excalidraw",
  "version": 2,
  "source": "https://github.com/zsviczian/obsidian-excalidraw-plugin",
  "elements": [],
  "appState": {
    "gridSize": null,
    "viewBackgroundColor": "#ffffff"
  },
  "files": {}
}
```

Requirements:

- `type` must be `excalidraw`
- `version` must be `2`
- `source` should point to the Obsidian Excalidraw plugin
- `elements` must contain visible elements
- `files` should remain `{}` unless binary assets are actually embedded

## Minimum element fields

Different element types need different extras, but these fields are the usual baseline:

```json
{
  "id": "unique-id",
  "type": "rectangle",
  "x": 120,
  "y": 120,
  "width": 220,
  "height": 88,
  "angle": 0,
  "strokeColor": "#163b66",
  "backgroundColor": "#dbeafe",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "groupIds": [],
  "roundness": { "type": 3 },
  "seed": 100101,
  "version": 1,
  "versionNonce": 100101,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1,
  "link": null,
  "locked": false
}
```

Practical rules:

- every `id` must be unique
- use stable integer values for `seed` and `versionNonce`
- prefer `roughness: 0` for cleaner exports
- default `opacity` to `100`
- use `boundElements: null` when nothing is bound

## Text elements

```json
{
  "id": "title-text",
  "type": "text",
  "x": 160,
  "y": 48,
  "width": 260,
  "height": 40,
  "angle": 0,
  "strokeColor": "#163b66",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 1,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "groupIds": [],
  "roundness": null,
  "seed": 100102,
  "version": 1,
  "versionNonce": 100102,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1,
  "link": null,
  "locked": false,
  "text": "Order Processing Flow",
  "fontSize": 28,
  "fontFamily": 2,
  "textAlign": "center",
  "verticalAlign": "middle",
  "baseline": 24,
  "containerId": null,
  "originalText": "Order Processing Flow",
  "lineHeight": 1.25
}
```

Text rules:

- do not drop body text below `16`
- default to `fontFamily: 2` unless the target environment has verified support for another value
- preserve the meaning of technical identifiers, field names, and APIs
- wrap long text before making containers excessively wide

## Arrows and bindings

Prefer real bindings over visual guesswork.

```json
{
  "id": "flow-arrow-1",
  "type": "arrow",
  "x": 300,
  "y": 200,
  "width": 180,
  "height": 0,
  "angle": 0,
  "strokeColor": "#215d8f",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "groupIds": [],
  "roundness": null,
  "seed": 100201,
  "version": 1,
  "versionNonce": 100201,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1,
  "link": null,
  "locked": false,
  "points": [[0, 0], [180, 0]],
  "startBinding": {
    "elementId": "node-a",
    "focus": 0,
    "gap": 4
  },
  "endBinding": {
    "elementId": "node-b",
    "focus": 0,
    "gap": 4
  },
  "startArrowhead": null,
  "endArrowhead": "arrow"
}
```

If a straight line crosses through important elements, switch to a routed multi-segment path.

## Text rendering stability

- keep complex labels compact
- check exports carefully when labels include many punctuation marks or long technical strings
- if the selected font renders poorly, prioritize legibility over stylistic consistency
- preserve JSON keys, event names, and method names exactly when they appear as evidence

## File-level export hint

The Obsidian Excalidraw plugin supports file-level export control:

- `excalidraw-autoexport: png`
- valid values typically include `none`, `png`, `svg`, and `both`

This skill defaults to `png`, but successful export still depends on a working `obsidian command` flow plus screenshot or image validation.
