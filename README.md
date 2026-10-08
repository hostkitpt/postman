# Hostkit API v2 for Postman

Import `postman.yaml` into Postman to use the Hostkit API v2.

- Full documentation: https://docs.hostkit.pt
- LLMs index: https://docs.hostkit.pt/llms.txt

## Setup

1. Download `postman.yaml` from this repository.
2. In Postman, select **Import** and choose the file.
3. Open the **Hostkit API v2** collection variables.
4. Set `apiKey` and `apiSecret` locally using credentials generated in Hostkit -> My Account
5. Keep `baseUrl` as `https://app.hostkit.pt/api/v2`.

The collection generates a fresh timestamp, nonce and HMAC signature before each request. Do not manually set signature values. No separate environment is required.

Never commit or share real credentials. Review write operations before sending them; do not retry uncertain creations without checking the result.

## Creating Documents

`addExpense` and `addInvoice` require a `lines` array with 1 to 20 lines. The document and all lines are created together; a line failure rolls back the complete creation. The signed JSON body must fit 8192 bytes.

Invoices remain drafts until explicitly finalized with `closeInvoice`. Separate line-creation endpoints are not available in API v2.

## Disclaimer

Hostkit is not responsible for API misuse, incorrect implementations or unintended actions caused by third-party code.
