---
kind: alternative
routes:
  web: Web
steps:
- text: 'The User types "dark" in the command palette and picks Theme: Dark'
  kind: actor
  actor: user
  entities: []
  contexts:
    web:
      place: web::signed-in::command-palette
- text: The Product applies the theme on this device
  kind: product
  actor: user
  entities:
  - {entity: device-settings, effect: changes, facts: [Theme]}
  - {entity: device, effect: reads, facts: []}
  contexts:
    web:
      place: web::signed-in::command-palette
---

# Pick a theme from the command palette

## Trigger

The user wants dark mode now.

## Outcome

Mitra is dark on this device.

## Edge cases

- The palette offers only values the user has not chosen already.
