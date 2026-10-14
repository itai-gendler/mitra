---
appliesTo:
- type: entity
  id: event
  effect: changes
  facts: [Title]
permits:
- related:
  - {verb: holds, entity: calendar}
  - {verb: has, entity: integration}
  - {verb: owns, entity: user}
  when:
  - {entity: integration, fact: Provider, is-not: Tempo}
- unattended: true
references:
- kind: code
  role: implementation
  target: src/integrations/tempo/Tempo.ts
- kind: doc
  role: intent
  target: docs/integrations/tempo.md
  title: Tempo
---

# A booked worklog's title is not changed from Mitra

In a Tempo calendar the title belongs to the Jira issue the time is booked on, so a saved worklog's title cannot be edited; its description, the worklog's note, can. Once the time is booked, Mitra replaces the typed title with the issue's key and summary.
