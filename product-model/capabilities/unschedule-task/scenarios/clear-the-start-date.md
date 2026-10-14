---
kind: alternative
routes:
  web: Web
steps:
- text: The User presses the cross beside the start date
  kind: actor
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Start]}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product unschedules the task and opens the Planning tab
  kind: product
  actor: user
  entities:
  - {entity: task, effect: changes, facts: [Start, End, Estimate, Reminders]}
  contexts:
    web:
      place: web::signed-in::planning-tab
---

# Unschedule from the editor

## Trigger

The user is in the task's editor.

## Outcome

The task is unscheduled and the Planning tab opens with the task still open.
