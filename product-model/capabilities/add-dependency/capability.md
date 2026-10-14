---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/relations/server/relations.ts#assertRelationsValid
- kind: code
  role: implementation
  target: src/features/relations/client/RelationsField.ts
- kind: code
  role: implementation
  target: src/features/relations/client/EntryConnections.ts
- kind: doc
  role: intent
  target: docs/dependencies.md
  title: Dependencies
---

# Add dependency

Make an entry wait for another: press the plus on Blocked by in the waiting entry's editor and search the user's visible calendars, or, with a mouse, draw the short line at the end of the first entry onto the one that should wait for it in the week or month view. The other entry then lists it under Blocks.
