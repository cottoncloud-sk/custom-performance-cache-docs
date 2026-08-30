# Compatibility and production verification

## Documented baseline

The canonical product page currently states:

- WordPress `6.4+`
- PHP `8.1+`
- write access for cache files according to the hosting configuration

This document was reviewed against the public product version `1.0.286` on
2026-08-30. A version number here means the documentation was checked against
that public version; it does not claim that every hosting, theme or plugin
combination has been tested.

## Per-site checks that remain mandatory

Before production enablement, record and test:

- homepage and representative public content;
- cart, checkout and account routes when WooCommerce is present;
- login/logout and authenticated pages;
- every important form and its success/error states;
- REST and AJAX consumers used by the theme or plugins;
- multilingual variants and canonical links;
- first visit and repeat visit on desktop, tablet and mobile;
- response headers or diagnostics that distinguish a cache HIT, MISS and BYPASS.

## Hosting and cache layers

The effective cache path may also include a host-level page cache, reverse
proxy, CDN, object cache or PHP opcode cache. Identify those layers before
changing settings. Never assume that a successful response proves which layer
served it.

Redis or another persistent object cache is an optional infrastructure layer,
not a universal requirement. Availability and safe configuration depend on the
hosting environment and the site workload.

## Fail-closed rule

If a request is authenticated, stateful, mutating or cannot be classified with
confidence, bypass page cache. A slower correct response is preferable to a
fast response containing stale or user-specific state.
