---
appliesTo:
- type: entity
  id: participant
  effect: removes
permits:
- related:
  - {verb: invites, entity: event}
  - {verb: holds, entity: calendar}
  - &id001 {verb: has, entity: integration}
  - &id002 {verb: owns, entity: user}
  when:
  - {entity: event, fact: Organized by someone else, is: 'No'}
  - &id003 {entity: calendar, fact: Read-only, is: 'No'}
- related:
  - {verb: invites, entity: task}
  - {verb: holds, entity: calendar}
  - *id001
  - *id002
  when:
  - {entity: task, fact: Organized by someone else, is: 'No'}
  - *id003
references:
- kind: code
  role: implementation
  target: src/features/entries/server/entries.ts#entriesRouter
- kind: doc
  role: intent
  target: docs/participants.md
  title: Participants
---

# Only the organizer removes participants

Taking people off an entry is the organizer's.
