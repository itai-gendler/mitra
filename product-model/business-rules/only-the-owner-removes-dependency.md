---
appliesTo:
- type: entity
  id: dependency
  effect: removes
permits:
- related:
  - {verb: waits through, entity: task}
  - {verb: holds, entity: calendar}
  - &id001 {verb: has, entity: integration}
  - &id002 {verb: owns, entity: user}
  when:
  - &id003 {entity: calendar, fact: Read-only, is: 'No'}
- related:
  - {verb: waits through, entity: event}
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

# Only the owner of the entry that keeps them removes dependencies, in a writable calendar

Removing dependencies from either side edits the entry that keeps them.
