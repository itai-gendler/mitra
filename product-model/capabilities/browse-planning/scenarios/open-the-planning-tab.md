---
kind: primary
routes:
  web: Web
steps:
- text: The User switches the sidebar to Planning
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::planning-tab
- text: The Product lists the overdue tasks and then the unscheduled ones
  kind: product
  actor: user
  entities:
  - {entity: task, effect: reads, facts: [Title, Due date, Estimate, Planning order, Overdue]}
  contexts:
    web:
      place: web::signed-in::planning-tab
---

# Open the Planning tab

## Trigger

The user plans the coming week.

## Outcome

The user sees their overdue tasks and every unscheduled task, each with its flag and estimate.

## Edge cases

- A task due this morning becomes overdue only tomorrow: whole days count.
- A task with no due date is overdue once the last day of its schedule has passed.
