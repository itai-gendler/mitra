---
kind: alternative
routes:
  web: Web
steps:
- text: The User clicks into the location field and types
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product suggests places used recently in the user's own calendars and, from the second letter, places from the geocoder, nearby ones first when the browser shares its position
  kind: product
  actor: user
  entities:
  - {entity: event, effect: reads, facts: [Location]}
  - {entity: calendar, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The User picks a suggestion
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::entry-editor
- text: The Product saves its name and address as the location
  kind: product
  actor: user
  entities:
  - {entity: event, effect: changes, facts: [Location]}
  contexts:
    web:
      place: web::signed-in::entry-editor
---

# Pick a suggested location

## Trigger

The user starts typing a place into the location field.

## Outcome

The location holds the picked place's name and address; a meeting link alone reads as Join with the service's name.

## Edge cases

- When the geocoder does not answer within five seconds, only recent places are suggested and anything typed is still kept.
