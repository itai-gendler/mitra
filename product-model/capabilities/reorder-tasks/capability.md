---
availability:
- {place: 'web::signed-in'}
domain: planning
references:
- kind: code
  role: implementation
  target: src/features/planning/client/Planning.ts
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
- kind: code
  role: implementation
  target: src/features/entries/EntryRank.ts
---

# Reorder tasks

Put the Unscheduled list in an order of the user's own by dragging tasks up or down. The order is kept by Mitra, so other apps do not see it.
