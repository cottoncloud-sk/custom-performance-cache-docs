# Sanitized safe-exclusion patterns

These examples describe classification logic, not copy-paste production rules.
Route names, cookies and integrations differ between sites.

## Bypass by request method

Cache only safe public reads. Bypass non-`GET` and non-`HEAD` requests unless a
specific integration has a stronger verified contract.

## Bypass authenticated or stateful sessions

Common bypass signals include:

- an authenticated WordPress session;
- a non-empty cart or customer-session cookie;
- a preview, password-protected or editor context;
- a nonce-bearing request;
- a route rendering customer-specific data.

Cookie names are implementation details. Match the exact installed stack; do
not publish or copy real customer cookie values.

## Bypass critical routes

Typical categories are:

```text
/wp-admin/
/wp-login.php
/cart/
/checkout/
/my-account/
REST requests that expose dynamic state
AJAX endpoints
form submission and confirmation routes
```

Localized slugs and custom endpoints must be discovered from the actual site.

## Verification matrix

For each critical journey, verify:

| State | First request | Repeat request | Expected result |
|---|---|---|---|
| Anonymous public page | MISS or generated | eligible HIT | identical public content |
| Logged-in page | BYPASS | BYPASS | correct account-specific content |
| Empty cart | BYPASS where state is created | BYPASS | cart remains correct |
| Non-empty cart | BYPASS | BYPASS | item, price and quantity remain correct |
| Form submit | BYPASS | BYPASS | validation and success state work |
| REST/AJAX dynamic request | BYPASS | BYPASS | fresh response, no cached mutation |

Record the preimage, changed setting and inverse action before enabling the
layer. After rollback, rerun the same matrix; switching a setting back is not
enough without a readback.

