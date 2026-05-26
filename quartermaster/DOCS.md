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

## OpenFoodFacts Contributions

To store per-user OpenFoodFacts credentials for product contributions, set `off_credential_encryption_key` to a long random secret in the App configuration and restart the App.

Keep this value stable. Quartermaster uses it to encrypt saved OpenFoodFacts passwords; changing it later prevents existing saved passwords from being decrypted.

## Recipes, AI, and Suppliers

Saved recipes and supplier review flows work without external AI credentials.

To enable AI-generated pantry recipe ideas, set `ai_provider` to `openrouter`, set `ai_model` to an OpenRouter model id, and provide `ai_openrouter_api_key`. Leave `ai_openrouter_base_url` at the default unless you are using a compatible proxy. Keep `ai_retain_raw_responses` disabled unless you are deliberately debugging provider responses.

To store household supplier credentials, set `supplier_credential_encryption_key` to a long random secret and restart the App.

Keep this value stable. Quartermaster uses it to encrypt saved supplier credentials; changing it later prevents existing saved credentials from being decrypted.
