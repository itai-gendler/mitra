---
kind: primary
routes:
  web: Web
steps:
- text: The User turns on the Hide done setting
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Hide done tasks]}
  contexts:
    web:
      place: web::signed-in::calendar-settings
- text: The Product saves the choice with the user's account
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Hide done tasks]}
  contexts:
    web:
      place: web::signed-in::calendar-settings
---

# Hide done tasks

## Trigger

Finished tasks clutter the week.

## Outcome

Done and cancelled tasks leave the week, month and year views and the Planning tab; search and the table still find them, and they still count towards their bigger task.

## Edge cases

- A task the user has open stays in sight until it is closed.
