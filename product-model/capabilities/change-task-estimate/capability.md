---
availability:
- {place: 'web::signed-in'}
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: code
  role: implementation
  target: src/features/entries/Entry.ts#Entry
- kind: doc
  role: intent
  target: docs/planning.md
  title: Planning
---

# Change task estimate

Say how long an unscheduled task will take in its Estimate field, by typing hours and minutes or picking a length. Only unscheduled tasks have an estimate.
