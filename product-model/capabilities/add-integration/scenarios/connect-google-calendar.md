---
kind: alternative
routes:
  web: Web
steps:
- text: The User chooses Google Calendar and presses Continue with Google
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User picks an account at Google and lets Mitra see and change their calendars
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product keeps the grant on the server, finds the account's calendars and brings the user back to them
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: creates, facts: [Provider, Connection details, Secret, Order]}
  - {entity: calendar, effect: creates, to: Turned off, facts: [Name, Provider name, Color, Holds, Read-only, Hidden, Order], with: integration}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User keeps the calendars ticked and presses Save
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product turns them on and imports them
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: changes, from: Turned off, to: Importing, facts: []}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Connect a Google account

## Trigger

The user's calendars are in Google.

## Outcome

The Google account is connected with its own grant, and its calendars are listed to choose from.

## Edge cases

- Connecting the same Google account again renews its grant instead of adding it twice.
- While the server has no Google client ID and secret, choosing Google Calendar shows a note that it is not configured instead.
