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

## Creating Documents

`addExpense` and `addInvoice` require a `lines` array with 1 to 20 lines. The document and all lines are created together; a line failure rolls back the complete creation. The signed JSON body must fit 8192 bytes.

`addInvoice` finalizes the invoice before committing and returns its `id`, `invoice_token` and `invoice_url`. Signing or finalization failures roll back the complete creation. Separate line-creation, invoice-closing and invoice-deletion endpoints are not available in API v2. Use a credit note when a closed invoice needs to be reversed.

## Invoicing

Customer requests list, create and delete customers. Deletion is refused when any fiscal document, including a draft, references the customer.

Current Account requests return period transactions and opening/closing balances, and manage unlinked manual transactions only. Dates use Unix seconds and amounts use decimal strings.

`addModelo30Transaction` creates a one-period (`U`) or recurring (`R`) transaction, without generating or submitting a declaration.

## Disclaimer

Hostkit is not responsible for API misuse, incorrect implementations or unintended actions caused by third-party code.
