---
appliesTo:
- type: entity
  id: task
  effect: creates
permits:
- related:
  - {verb: holds, entity: calendar}
  - {verb: has, entity: integration}
  - {verb: owns, entity: user}
  when:
  - {entity: calendar, fact: Read-only, is: 'No'}
- unattended: true
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
- kind: doc
  role: intent
  target: docs/calendars.md
  title: Calendars
---

# Only the owner adds tasks, and only in a calendar that is not read-only

A user adds tasks only in their own calendars, and never in a read-only one, such as a subscription or a calendar shared to view only. Syncing brings the provider's own changes in whatever the calendar allows Mitra.
