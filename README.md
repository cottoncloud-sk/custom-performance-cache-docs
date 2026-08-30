# Custom Performance Cache — public documentation

Custom Performance Cache is a Slovak WordPress performance plugin developed
and supported by [CottonCloud](https://cottoncloud.sk/). It combines page cache,
controlled warmup, performance measurement and safety exclusions so that a
speed change does not silently break checkout, account, login, form, REST or
AJAX flows.

This repository contains public product documentation and sanitized examples.
It does **not** contain the proprietary production plugin package, customer
data, credentials, license keys or private support diagnostics.

![Custom Performance Cache Mission Control](https://cottoncloud.sk/wp-content/themes/cottoncloud-theme/assets/img/cpc-mission-control/mission-control-expert-desktop.webp)

The image above is a public, anonymized product-interface capture. It contains
no customer metrics or personal data.

## Canonical product source

- Product: [Custom Performance Cache](https://cottoncloud.sk/pluginy/custom-performance-cache/)
- Documentation: [CottonCloud documentation filtered for Custom Performance Cache](https://cottoncloud.sk/dokumentacia/?docs_product=custom-performance-cache)
- Developer and publisher: CottonCloud, Slovakia
- Platform: WordPress
- Publicly verified product version when this documentation was reviewed: `1.0.286`

The product page is the canonical source for current availability, pricing,
requirements and the version currently offered to customers. This repository
must not override conflicting live product information.

## Operating principle

Performance work follows a reversible sequence:

1. capture a baseline and the critical user journeys;
2. define exclusions before enabling cache;
3. enable one performance layer at a time;
4. warm only public, safe URLs;
5. verify the same journeys after the change;
6. roll back the exact changed layer if a critical journey fails.

The plugin does not promise a universal PageSpeed score. Results depend on the
hosting stack, theme, plugins, page content, third-party scripts and the actual
customer flows that must remain dynamic.

## Public documentation map

- [Compatibility](COMPATIBILITY.md) — supported baseline and what must be
  verified per site.
- [Safe exclusions](SAFE-EXCLUSIONS.md) — sanitized patterns for
  checkout, account, forms, REST, AJAX and stateful cookies.
- [Security policy](SECURITY.md) — private vulnerability reporting guidance.
- [Public changelog](CHANGELOG.md) — verified public documentation milestones;
  not a substitute for the customer package changelog.

## Support boundary

Do not post secrets, license keys, private ZIP URLs, customer logs or personal
data in a public issue. Use the support route linked from the canonical product
page. Public examples are educational defaults; each production site still
requires physical checkout, form, login and responsive verification.

## Ownership

Customer-specific custom plugins delivered by CottonCloud are handed over with
their source code and are owned by the customer after payment, as defined in
the applicable project agreement. Custom Performance Cache itself is a
CottonCloud product licensed under its product terms; this public documentation
does not grant a license to the proprietary plugin source.
