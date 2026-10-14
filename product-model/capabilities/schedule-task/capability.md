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
---

# Schedule task

Give an unscheduled task a start and an end that fit its constraints: drag it out of the Planning tab into a view, or press Start date in its editor. The estimate becomes the length of the schedule.
