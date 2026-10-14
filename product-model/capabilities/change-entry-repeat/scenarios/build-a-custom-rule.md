---
kind: alternative
routes:
  web: Web
steps:
- text: The User picks Custom…, sets every 2 weeks on Thursday, ends on a date, and presses Done
  kind: actor
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves the rule
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Repeat]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Build a custom rule

## Trigger

A class meets every two weeks on Thursday until December.

## Outcome

The Repeat row reads the rule back, such as "Every 2 weeks on Thu until Dec 18".

## Edge cases

- A weekly rule keeps at least one day turned on.
