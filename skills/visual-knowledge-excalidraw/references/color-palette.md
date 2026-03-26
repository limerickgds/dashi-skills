# Excalidraw Semantic Palette

Choose colors by semantic role first and aesthetics second.

## Text hierarchy

| Purpose | Color | Notes |
|---------|-------|-------|
| Main title | `#163b66` | Strong focal title color |
| Region title | `#215d8f` | Section headers and lane titles |
| Body text | `#2f3a45` | Default node and label text |
| Secondary notes | `#5f6b76` | Supporting annotation text |
| Emphasis | `#b45309` | Important highlights |
| Error / risk text | `#9f1239` | Failures, risks, blocked states |

## Primary node fills

| Semantic role | Fill color | Typical use |
|---------------|------------|-------------|
| Input / entry | `#dbeafe` | Inputs, entry points, triggers |
| Processing / orchestration | `#ede9fe` | Processing stages, service orchestration |
| Success / output | `#dcfce7` | Outputs, successful end states |
| Decision / branch | `#fef3c7` | Decisions, routing points |
| Risk / failure | `#ffe4e6` | Errors, alerts, failure states |
| Data / storage | `#d1fae5` | Databases, caches, queues, storage |
| Analysis / evidence | `#fae8ff` | Metrics, analysis, evidence blocks |

## Large region backgrounds

| Region type | Fill color | Notes |
|-------------|------------|-------|
| UI / edge layer | `#eff6ff` | User-facing or edge interactions |
| Application / logic layer | `#f5f3ff` | Business logic and services |
| Data / infrastructure layer | `#ecfdf5` | Storage, cache, queues, infrastructure |
| Reliability / ops layer | `#fff1f2` | Monitoring, alerting, compensation |

Recommended region styling:

- `fillStyle: "solid"`
- `opacity: 35-50`
- lighter border weight than primary nodes

## Arrows and lines

| Purpose | Color | Notes |
|---------|-------|-------|
| Primary flow | `#215d8f` | Main reading path |
| Data flow | `#0f766e` | Data movement, event streams |
| Failure / rollback | `#be123c` | Failure, compensation, alert paths |
| Weak / optional relation | `#64748b` | Secondary relations, often dashed |

## Evidence blocks

Use dark evidence blocks for concrete payloads, APIs, event names, or examples.

| Element | Color |
|---------|-------|
| Evidence background | `#1f2937` |
| Evidence title text | `#f8fafc` |
| Evidence body text | `#e2e8f0` |
| JSON / field highlight | `#93c5fd` |
| Error / risk highlight | `#fca5a5` |
| Success / normal-state highlight | `#86efac` |

## Palette rules

- avoid text lighter than `#5f6b76` on a white background
- prefer darker text on light node fills
- keep the number of dominant semantic colors limited
- reserve risk colors for actual failure paths and risky states
- if contrast is weak in the export, increase text and line contrast before changing the whole palette
