---
kind: alternative
routes:
  web: Web
steps:
- text: The User turns off Connector lines in the month view
  kind: actor
  actor: user
  entities:
  - {entity: device-settings, effect: reads, facts: [Connector lines in the month view]}
  contexts:
    web:
      place: web::signed-in::calendar-settings
- text: The Product saves the choice on this device
  kind: product
  actor: user
  entities:
  - {entity: device-settings, effect: changes, facts: [Connector lines in the month view]}
  - {entity: device, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendar-settings
---

# Turn off connector lines in the month view

## Trigger

Lines crowd the month view.

## Outcome

The month view on this device draws no lines between subtasks and dependencies.
