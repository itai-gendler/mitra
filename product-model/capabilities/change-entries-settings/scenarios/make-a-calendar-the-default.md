---
kind: alternative
routes:
  web: Web
steps:
- text: The User clicks the work calendar's icon in the sidebar
  kind: actor
  actor: user
  entities:
  - {entity: user, effect: reads, facts: [Default calendar]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The Product makes it the default calendar
  kind: product
  actor: user
  entities:
  - {entity: user, effect: changes, facts: [Default calendar]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Make a calendar the default from the sidebar

## Trigger

Most new entries belong in the work calendar.

## Outcome

The work calendar's icon is filled, and new entries go there unless the user picks another.

## Edge cases

- Clicking the default's icon again clears it; without a default, new entries go to the first calendar showing.
