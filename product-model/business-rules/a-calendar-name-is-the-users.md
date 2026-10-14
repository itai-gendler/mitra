---
appliesTo:
- type: entity
  id: calendar
  effect: changes
  facts: [Name]
references:
- kind: code
  role: implementation
  target: src/features/sources/Source.ts#Source
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# A calendar's name is the user's

Syncing never overwrites a name the user gave; Mitra takes the provider's name again only when the calendar is actually renamed there.
