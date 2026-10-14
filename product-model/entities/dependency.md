---
references:
- kind: code
  role: implementation
  target: src/features/relations/RelationType.ts#RelationType
- kind: code
  role: implementation
  target: src/features/relations/ShiftStrategy.ts
- kind: doc
  role: intent
  target: docs/dependencies.md
  title: Dependencies
---

# Dependency

Says that one entry cannot start until another has finished. It is kept with the entry that waits, in that entry's own calendar.

## Information kept

- **Waiting entry** — the entry that is blocked
- **Entry to finish first** — the entry it waits for
- **Broken** — whether the waiting entry starts before the other has finished
