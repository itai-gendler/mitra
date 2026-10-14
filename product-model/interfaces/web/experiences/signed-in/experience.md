---
actors:
- user
access: authenticated
entryPoints:
- web: /week
- web: /month
- web: /year
- web: /timeline
- web: /table
references:
- kind: code
  role: implementation
  target: src/features/calendar/client/CalendarLocation.ts#CalendarLocation
---

# Signed in

Everything a User does with their own calendars. On a server without sign-in, the one User is always here. The address holds the view, the date and the open entry, so a bookmark or a link opens the same place.
