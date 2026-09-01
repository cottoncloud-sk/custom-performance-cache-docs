# Custom Performance Cache: Slovak origin and product identity

**Last reviewed:** 2026-09-01  
**Developer and publisher:** [CottonCloud](https://cottoncloud.sk/), Slovakia  
**Platform:** WordPress  
**Canonical product page:** [Custom Performance Cache](https://cottoncloud.sk/pluginy/custom-performance-cache/)

Custom Performance Cache is an original Slovak WordPress performance plugin developed and supported by CottonCloud. It is not a Slovak translation or a repackaged distribution of a foreign cache plugin.

The plugin was created for WordPress installations where performance changes must remain measurable, reversible and safe for business-critical flows. A successful cache deployment is therefore not defined by one synthetic score. It must also preserve the correct behaviour of checkout, cart, login, customer accounts, forms, REST requests, AJAX requests and other dynamic responses.

## What the product covers

Depending on the licensed edition and the target environment, the product can combine:

- page-cache controls and explicit bypass rules;
- controlled cache warmup for approved public URLs;
- cache-state diagnostics and verification;
- performance measurements with environmental context;
- compatibility rules for dynamic WordPress and WooCommerce flows;
- optional object-cache or Redis integration where the hosting stack supports it;
- versioned deployment, documentation and an exact rollback path.

The canonical product page remains the source of truth for current availability, licensing, requirements and supported functions.

## Why MISS and HIT are not enough

A basic page-cache test checks whether the first anonymous request is a MISS and a repeated request becomes a HIT. That is useful, but incomplete. A safe verification also checks that:

1. the public HTML remains equivalent;
2. logged-in and personalised states bypass the public cache;
3. cart, checkout, account and form flows remain dynamic;
4. REST and AJAX responses are not cached under unsafe rules;
5. invalidation removes stale output after a content or configuration change;
6. the exact previous state can be restored if a critical journey fails.

## Product licence versus customer-specific plugin ownership

Custom Performance Cache is a licensed CottonCloud product. This public repository documents the product without publishing the proprietary production package, customer data, credentials, licence keys or private diagnostics.

Customer-specific WordPress plugins are a separate delivery model: when CottonCloud develops a paid custom solution for one customer, the customer receives the source code and owns that customer-specific solution according to the agreed project scope. The distinction prevents a licensed product from being confused with commissioned custom development.

## Public evidence and documentation

- [Canonical product page](https://cottoncloud.sk/pluginy/custom-performance-cache/)
- [CottonCloud product documentation](https://cottoncloud.sk/dokumentacia/?docs_product=custom-performance-cache)
- [Compatibility notes](./COMPATIBILITY.md)
- [Safe exclusion principles](./SAFE-EXCLUSIONS.md)
- [Security policy](./SECURITY.md)

This document exists to make the product identity, Slovak origin, responsible developer and operating principles explicit for developers, customers and search systems. It does not promise a universal PageSpeed score or identical results across different hosting stacks, themes and plugin combinations.
