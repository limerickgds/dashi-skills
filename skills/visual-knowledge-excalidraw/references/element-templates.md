# Common Element Templates

Use these as starting structures. Adjust coordinates, sizes, labels, and colors for the actual diagram.

## 1. Title band

```json
[
  {
    "id": "title-band",
    "type": "rectangle",
    "x": 80,
    "y": 32,
    "width": 1040,
    "height": 72,
    "angle": 0,
    "strokeColor": "#215d8f",
    "backgroundColor": "#eff6ff",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 60,
    "groupIds": [],
    "roundness": { "type": 3 },
    "seed": 110001,
    "version": 1,
    "versionNonce": 110001,
    "isDeleted": false,
    "boundElements": [{ "id": "title-text", "type": "text" }],
    "updated": 1,
    "link": null,
    "locked": false
  },
  {
    "id": "title-text",
    "type": "text",
    "x": 360,
    "y": 52,
    "width": 480,
    "height": 32,
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
    "seed": 110002,
    "version": 1,
    "versionNonce": 110002,
    "isDeleted": false,
    "boundElements": null,
    "updated": 1,
    "link": null,
    "locked": false,
    "text": "Diagram Title",
    "fontSize": 28,
    "fontFamily": 2,
    "textAlign": "center",
    "verticalAlign": "middle",
    "baseline": 24,
    "containerId": "title-band",
    "originalText": "Diagram Title",
    "lineHeight": 1.25
  }
]
```

## 2. Standard node rectangle

```json
[
  {
    "id": "node-1",
    "type": "rectangle",
    "x": 120,
    "y": 180,
    "width": 220,
    "height": 84,
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
    "seed": 120001,
    "version": 1,
    "versionNonce": 120001,
    "isDeleted": false,
    "boundElements": [{ "id": "node-1-text", "type": "text" }],
    "updated": 1,
    "link": null,
    "locked": false
  },
  {
    "id": "node-1-text",
    "type": "text",
    "x": 160,
    "y": 208,
    "width": 140,
    "height": 28,
    "angle": 0,
    "strokeColor": "#2f3a45",
    "backgroundColor": "transparent",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 100,
    "groupIds": [],
    "roundness": null,
    "seed": 120002,
    "version": 1,
    "versionNonce": 120002,
    "isDeleted": false,
    "boundElements": null,
    "updated": 1,
    "link": null,
    "locked": false,
    "text": "Node Label",
    "fontSize": 18,
    "fontFamily": 2,
    "textAlign": "center",
    "verticalAlign": "middle",
    "baseline": 16,
    "containerId": "node-1",
    "originalText": "Node Label",
    "lineHeight": 1.25
  }
]
```

## 3. Decision diamond

```json
[
  {
    "id": "decision-1",
    "type": "diamond",
    "x": 420,
    "y": 170,
    "width": 200,
    "height": 110,
    "angle": 0,
    "strokeColor": "#b45309",
    "backgroundColor": "#fef3c7",
    "fillStyle": "solid",
    "strokeWidth": 2,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 100,
    "groupIds": [],
    "roundness": null,
    "seed": 130001,
    "version": 1,
    "versionNonce": 130001,
    "isDeleted": false,
    "boundElements": [{ "id": "decision-1-text", "type": "text" }],
    "updated": 1,
    "link": null,
    "locked": false
  },
  {
    "id": "decision-1-text",
    "type": "text",
    "x": 470,
    "y": 208,
    "width": 100,
    "height": 28,
    "angle": 0,
    "strokeColor": "#2f3a45",
    "backgroundColor": "transparent",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 100,
    "groupIds": [],
    "roundness": null,
    "seed": 130002,
    "version": 1,
    "versionNonce": 130002,
    "isDeleted": false,
    "boundElements": null,
    "updated": 1,
    "link": null,
    "locked": false,
    "text": "Decision",
    "fontSize": 18,
    "fontFamily": 2,
    "textAlign": "center",
    "verticalAlign": "middle",
    "baseline": 16,
    "containerId": "decision-1",
    "originalText": "Decision",
    "lineHeight": 1.25
  }
]
```

## 4. Connecting arrow

```json
{
  "id": "arrow-1",
  "type": "arrow",
  "x": 340,
  "y": 222,
  "width": 80,
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
  "seed": 140001,
  "version": 1,
  "versionNonce": 140001,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1,
  "link": null,
  "locked": false,
  "points": [[0, 0], [80, 0]],
  "startBinding": {
    "elementId": "node-1",
    "focus": 0,
    "gap": 4
  },
  "endBinding": {
    "elementId": "decision-1",
    "focus": 0,
    "gap": 4
  },
  "startArrowhead": null,
  "endArrowhead": "arrow"
}
```

To route around an element, use a multi-segment path such as:

```json
"points": [[0, 0], [120, 0], [120, 80], [220, 80]]
```

## 5. Lane / region background

```json
[
  {
    "id": "lane-frontend",
    "type": "rectangle",
    "x": 80,
    "y": 140,
    "width": 320,
    "height": 520,
    "angle": 0,
    "strokeColor": "#93c5fd",
    "backgroundColor": "#eff6ff",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "dashed",
    "roughness": 0,
    "opacity": 45,
    "groupIds": [],
    "roundness": { "type": 3 },
    "seed": 150001,
    "version": 1,
    "versionNonce": 150001,
    "isDeleted": false,
    "boundElements": [{ "id": "lane-frontend-title", "type": "text" }],
    "updated": 1,
    "link": null,
    "locked": false
  },
  {
    "id": "lane-frontend-title",
    "type": "text",
    "x": 116,
    "y": 158,
    "width": 140,
    "height": 24,
    "angle": 0,
    "strokeColor": "#215d8f",
    "backgroundColor": "transparent",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 100,
    "groupIds": [],
    "roundness": null,
    "seed": 150002,
    "version": 1,
    "versionNonce": 150002,
    "isDeleted": false,
    "boundElements": null,
    "updated": 1,
    "link": null,
    "locked": false,
    "text": "Frontend / Edge",
    "fontSize": 20,
    "fontFamily": 2,
    "textAlign": "left",
    "verticalAlign": "middle",
    "baseline": 18,
    "containerId": "lane-frontend",
    "originalText": "Frontend / Edge",
    "lineHeight": 1.25
  }
]
```

## 6. Evidence block

Use evidence blocks for payloads, APIs, event names, or concrete examples.

```json
[
  {
    "id": "evidence-box",
    "type": "rectangle",
    "x": 720,
    "y": 180,
    "width": 320,
    "height": 180,
    "angle": 0,
    "strokeColor": "#111827",
    "backgroundColor": "#1f2937",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 100,
    "groupIds": [],
    "roundness": { "type": 2 },
    "seed": 160001,
    "version": 1,
    "versionNonce": 160001,
    "isDeleted": false,
    "boundElements": [{ "id": "evidence-text", "type": "text" }],
    "updated": 1,
    "link": null,
    "locked": false
  },
  {
    "id": "evidence-text",
    "type": "text",
    "x": 744,
    "y": 204,
    "width": 272,
    "height": 132,
    "angle": 0,
    "strokeColor": "#e2e8f0",
    "backgroundColor": "transparent",
    "fillStyle": "solid",
    "strokeWidth": 1,
    "strokeStyle": "solid",
    "roughness": 0,
    "opacity": 100,
    "groupIds": [],
    "roundness": null,
    "seed": 160002,
    "version": 1,
    "versionNonce": 160002,
    "isDeleted": false,
    "boundElements": null,
    "updated": 1,
    "link": null,
    "locked": false,
    "text": "POST /api/orders\nEvent: order.created\nCache: order:{id}",
    "fontSize": 16,
    "fontFamily": 2,
    "textAlign": "left",
    "verticalAlign": "top",
    "baseline": 14,
    "containerId": "evidence-box",
    "originalText": "POST /api/orders\nEvent: order.created\nCache: order:{id}",
    "lineHeight": 1.25
  }
]
```

## Usage guidance

- keep primary nodes short
- move long detail into callouts or evidence blocks
- do not let evidence blocks outweigh the main flow
- get bindings and routing right before polishing alignment
