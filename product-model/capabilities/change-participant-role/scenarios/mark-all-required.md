---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Mark all required
  kind: actor
  actor: user
  entities:
  - {entity: participant, effect: reads, facts: [Role]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product sets every person's role to required
  kind: product
  actor: user
  entities:
  - {entity: participant, effect: changes, facts: [Role]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Mark everyone required

## Trigger

Everyone has to attend after all.

## Outcome

Every person is required.
