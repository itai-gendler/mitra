---
appliesTo:
- type: entity
  id: calendar
  effect: creates
references:
- kind: code
  role: implementation
  target: src/integrations/Integration.ts#Integration
- kind: doc
  role: intent
  target: docs/integrations/README.md
  title: Integrations
---

# Calendars that appear later arrive turned off

When an account is connected its calendars are listed all ticked; calendars that show up in the account afterwards arrive unticked, so nothing new lands on the user's calendar without their choosing it. Mitra never downloads a calendar that is turned off.
