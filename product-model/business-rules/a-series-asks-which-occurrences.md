---
appliesTo:
- type: capability
  id: edit-entry
- type: capability
  id: move-entry
- type: capability
  id: delete-entry
- type: capability
  id: move-entry-to-calendar
references:
- kind: code
  role: implementation
  target: src/features/recurrence/server/occurrences.ts
- kind: doc
  role: intent
  target: docs/repeats.md
  title: Repeats
---

# Changing an occurrence asks which occurrences are meant

Dragging, resizing, deleting or editing one occurrence of a series asks whether this entry, this and following entries, or all entries are meant; holding Ctrl skips the question and changes only this one. A change to the repeat rule always applies to the whole series. Marking a task occurrence done, and scheduling one occurrence of a task that repeats by its due date, apply to that occurrence alone. A deleted occurrence stays deleted.
