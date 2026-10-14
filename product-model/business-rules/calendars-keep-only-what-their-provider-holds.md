---
appliesTo:
- type: entity
  id: event
- type: entity
  id: task
- type: entity
  id: availability
references:
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
- kind: code
  role: implementation
  target: src/integrations/notion/Notion.ts
- kind: code
  role: implementation
  target: src/integrations/tempo/Tempo.ts
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# A calendar keeps only what its provider can store

Each provider stores different things, and Mitra hides the rows a calendar cannot store so nothing typed disappears on the next sync. Notion holds tasks with one date: no events, availability, due date, estimate, repeats, reminders, location, participants, time zone, progress, busy or free, visibility or cancelled status. Tempo holds timed worklogs on one day with no all-day entries, repeats, reminders, location, participants, links, busy or free, visibility or availability. Google Calendar holds no links and no progress. A change or move that would need what the destination cannot hold is refused.

## Rationale

Every change goes back to the calendar the entry belongs to, so a field the provider cannot keep would be lost on the next sync.
