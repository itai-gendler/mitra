---
appliesTo:
- type: entity
  id: subtask-link
  effect: creates
permits:
- related:
  - {verb: is a subtask through, entity: task}
  - {verb: holds, entity: calendar}
  - &id001 {verb: has, entity: integration}
  - &id002 {verb: owns, entity: user}
  when:
  - &id003 {entity: calendar, fact: Read-only, is: 'No'}
- related:
  - {verb: is a subtask through, entity: event}
  - {verb: holds, entity: calendar}
  - *id001
  - *id002
  when:
  - *id003
references:
- kind: code
  role: implementation
  target: src/features/relations/server/relations.ts#assertRelationsValid
---

# Only the owner of the entry that keeps them adds subtask links, in a writable calendar

Subtask links are kept with the entry that is the subtask or waits, in that entry's own calendar, which must take changes from Mitra.
