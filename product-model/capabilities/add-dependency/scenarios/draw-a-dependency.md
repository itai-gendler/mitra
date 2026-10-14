---
kind: alternative
routes:
  web: Web
steps:
- text: The User grabs the line at the end of the first entry and drops it on the entry that should wait
  kind: actor
  actor: user
  entities:
  - {entity: dependency, effect: reads, facts: [Broken]}
  contexts:
    web:
      place: web::signed-in::calendar-views
- text: The Product saves the dependency, red when the waiting entry already starts too early
  kind: product
  actor: user
  entities:
  - {entity: dependency, effect: creates, facts: [Waiting entry, Entry to finish first, Broken]}
  contexts:
    web:
      place: web::signed-in::calendar-views
---

# Draw a dependency

## Trigger

The user sees two entries in the week and wants one to follow the other.

## Outcome

The dependency is saved with the entry dropped on.
