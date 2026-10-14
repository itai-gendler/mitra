---
kind: alternative
routes:
  web: Web
steps:
- text: The User opens a webcal link, which opens the Calendar Subscription form with the address filled in
  kind: actor
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User checks the address and presses Connect
  kind: actor
  actor: user
  entities:
  - {entity: integration, effect: reads, facts: [Connection details]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product reads the feed and lists its calendar
  kind: product
  actor: user
  entities:
  - {entity: calendar, effect: reads, facts: [Name, Holds]}
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The User presses Save
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::integration-details
- text: The Product saves the subscription with its one calendar, read-only, and imports it
  kind: product
  actor: user
  entities:
  - {entity: integration, effect: creates, facts: [Provider, Connection details, Secret, Order]}
  - {entity: calendar, effect: creates, to: Importing, facts: [Name, Provider name, Color, Holds, Read-only, Hidden, Order], with: integration}
  contexts:
    web:
      place: web::signed-in::calendars-tab
---

# Subscribe to a calendar link

## Trigger

A sports club publishes its fixtures as a webcal link.

## Outcome

One read-only calendar mirrors the feed and takes its name and color.

## Edge cases

- Clicking the link never subscribes on its own: the feed is fetched only once the user presses Connect.
- A feed bigger than 20 MB is refused with "The calendar is too large to subscribe to".
- A feed that asks for a username and password is refused with "The calendar requires a username and password" until they are entered.
