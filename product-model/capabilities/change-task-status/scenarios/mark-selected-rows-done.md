---
kind: alternative
routes:
  web: Web
steps:
- text: The User selects task rows and presses Done in the bar above them
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::table-view
- text: The Product marks each selected task Done
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, from: Doing, to: Done, facts: [Progress]}
  contexts:
    web:
      place: web::signed-in::table-view
---

# Mark selected tasks done in the table

## Trigger

The user clears finished tasks at the end of the week.

## Outcome

Every selected task is Done; a repeating task's selected occurrence alone is marked.

## Edge cases

- Under All entries, a repeating entry stands for the whole series and the status buttons skip it.
