# Hostkit API v2 for Postman

Import `postman.yaml` into Postman to use the Hostkit API v2.

Official documentation: [Hostkit API v2](https://docs.hostkit.pt/).

## Setup

1. Download `postman.yaml` from this repository.
2. In Postman, select **Import** and choose the file.
3. Open the **Hostkit API v2** collection variables.
4. Set `apiKey` and `apiSecret` locally using credentials generated in Hostkit **My Account**.
5. Keep `baseUrl` as `https://app.hostkit.pt/api/v2`.

The collection generates a fresh timestamp, nonce and HMAC signature before each request. Do not manually set signature values. No separate environment is required.

Never commit or share real credentials. Review write operations before sending them; do not retry uncertain creations without checking the result.

For authentication, endpoints and troubleshooting, see the [Postman guide](https://docs.hostkit.pt/postman).
