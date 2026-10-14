---
kind: primary
routes:
  web: Web
steps:
- text: The User chooses Add Integration, then CalDAV
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
- text: The User enters the server URL, username and password and presses Connect
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Connection details]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product finds the account's calendars and lists them, all ticked, each saying what it holds
  kind: product
  actor: user
  entities:
  - {entity: calendar, as: ticked, effect: reads, facts: [Name, Holds]}
  - {entity: calendar, as: unticked, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User unticks one calendar and presses Save
  kind: actor
  actor: user
  entities:
  - {entity: calendar, as: unticked, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product saves the account with its calendars and starts importing the ticked ones
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: creates, facts: [Provider, Connection details, Secret, Order, Own addresses]}
  - {entity: calendar, as: ticked, effect: creates, to: Importing, facts: [Name, Provider name, Color, Holds, Read-only, Hidden, Order], with: integration}
  - {entity: calendar, as: unticked, effect: creates, to: Turned off, facts: [Name, Provider name, Color, Holds, Read-only, Hidden, Order], with: integration}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Connect a CalDAV account

## Trigger

The user keeps their calendars on their own CalDAV server.

## Outcome

The account sits in the sidebar with the calendars the user kept, importing and then syncing both ways.

## Edge cases

- Apple Calendar connects the same way with an Apple ID and an app-specific password.
- Calendars shared to view only are marked read-only on their own.
