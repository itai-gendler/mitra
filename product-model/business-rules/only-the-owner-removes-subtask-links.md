---
appliesTo:
- type: entity
  id: subtask-link
  effect: removes
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
  target: src/features/relations/client/RelationsField.ts
---

# Only the owner of the entry that keeps them removes subtask links, in a writable calendar

Removing subtask links from either side edits the entry that keeps them.
