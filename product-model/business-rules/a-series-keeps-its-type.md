---
appliesTo:
- type: capability
  id: change-entry-type
- type: entity
  id: event
- type: entity
  id: task
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
---

# A repeating entry keeps its type

The type of a repeating entry, and of an entry in a calendar that holds only one type, cannot change. Whatever the new type cannot hold is dropped when the type changes.
