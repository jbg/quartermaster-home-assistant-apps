# Quartermaster App

## Getting Started

1. Install and start the App.
2. Open the web UI.
3. Register the first account and create your household.

The default configuration stores data in `/data/data.db` inside the Home Assistant App data volume. Home Assistant backups include this data.

## Remote Access

For LAN-only dogfooding, the exposed `8080` port is enough.

For invite links, native app deep links, and access away from home, configure a public HTTPS origin and set `public_base_url` to that origin, for example:

```text
https://quartermaster.example.com
```

`public_base_url` must be an HTTPS origin with no path, query, or fragment.

## Reminder Options

Expiry reminders are enabled by default in this App profile. Reminder fire hour and minute are interpreted in each household's configured timezone.
