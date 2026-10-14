---
kind: primary
routes:
  web: Web
steps:
- text: The User picks Deutsch under Language
  kind: actor
  actor: user
  entities:
  - {entity: device-settings, effect: reads, facts: [Language]}
  contexts:
    web:
      place: web::signed-in::general-settings
- text: The Product applies the language on this device without reloading
  kind: product
  actor: user
  entities:
  - {entity: device-settings, effect: changes, facts: [Language]}
  - {entity: device, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::general-settings
---

# Switch the language

## Trigger

The user reads German more easily.

## Outcome

Mitra reads in German at once, with dates, times and weeks as in Germany.

## Edge cases

- A preview under the setting shows how dates, times, the week, numbers and time zone names read.
