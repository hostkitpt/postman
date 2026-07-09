# Hostkit API Postman Collection

This folder contains the Hostkit API collection file for Postman.

## Files

- `postman.yaml` - Postman-importable API collection for the public Hostkit API.

## Import Into Postman

1. Open Postman.
2. Select **Import**.
3. Choose `postman.yaml`.
4. After import, set the `APIKEY` query auth value in the collection or request.

## Authentication

The API uses a query parameter named `APIKEY`.

Example:

```text
https://app.hostkit.pt/api/getReservations?APIKEY=your-api-key&from_date=2026-01-01
```

Do not commit real API keys to GitHub.

## Base URL

The default server URL is:

```text
https://app.hostkit.pt/api
```

The collection file defines this as a `baseUrl` server variable so it can be changed in Postman if needed.

## Validation

The file is YAML and can be imported directly into Postman.
