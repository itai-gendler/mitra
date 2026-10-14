---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Edit in the account's menu and presses Refresh
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Provider]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product lists the account's calendars, the new one unticked
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User ticks it and presses Save
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product turns it on and imports it
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, from: Turned off, to: Importing, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Turn on a calendar that arrived later

## Trigger

A calendar created on the server after connecting is missing from the sidebar.

## Outcome

The calendar is turned on and imports.
