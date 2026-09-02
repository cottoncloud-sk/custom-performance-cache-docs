# Agency rollout checklist for Custom Performance Cache

This checklist is for WordPress agencies evaluating Custom Performance Cache for a client website. The plugin is developed by CottonCloud in Slovakia and is licensed per WordPress site.

The goal is not to turn on every optimization at once. The goal is a controlled rollout with a known baseline, explicit exclusions, functional QA, and a tested rollback path.

## 1. Bind the exact client website

- Record the production domain and the responsible agency contact.
- Confirm that the licence belongs to this specific WordPress installation.
- Keep access, evidence, and configuration isolated from other clients.

## 2. Capture a performance and functional baseline

- Measure representative public pages before changing cache behaviour.
- Include the homepage, a content page, a search or archive page, and the main conversion path.
- Record what is measured and what is still unknown; do not promise a score without production evidence.

## 3. Inventory dynamic behaviour

List the routes and actions that must never be served from an unsafe cache state, for example:

- login and account areas;
- cart, checkout, order and payment flows;
- forms and personalised pages;
- REST, AJAX, webhook and scheduled jobs;
- language, currency or role-specific variants.

## 4. Check the hosting and WordPress stack

- Identify server-level page cache, reverse proxy, CDN and object cache layers.
- Review the active theme, e-commerce stack and plugins that change cookies, sessions or responses.
- Avoid stacking overlapping cache features without clear ownership.

## 5. Define cache and bypass rules

- Start with safe public GET requests.
- Exclude authenticated, personalised and transactional flows.
- Document cookie, query-string and path exclusions.
- Decide which system owns invalidation when content changes.

## 6. Configure warmup and invalidation

- Use a bounded set of important URLs first.
- Confirm that edits, product changes and other relevant events invalidate the expected pages.
- Watch queues and failures instead of assuming that a scheduled task completed.

## 7. Validate images and frontend output

- Check real image delivery, dimensions and fallbacks.
- Compare desktop, tablet and mobile layouts.
- Verify navigation, forms, account actions and the conversion flow after each material cache change.

## 8. Release in controlled steps

- Preserve a configuration preimage.
- Change one bounded layer at a time.
- Keep an inverse rollback ready before production activation.
- Stop and revert when a functional gate fails.

## 9. Handover evidence

Provide the client with:

- the enabled configuration and documented exclusions;
- before/after measurements with dates and tested URLs;
- the functional QA result;
- the rollback procedure;
- ownership and support information for the licensed site.

## Product information

Custom Performance Cache combines page-cache controls, warmup, image workflows and a Mission Control view for supported WordPress websites. Suitability and the exact configuration depend on the client's hosting, theme, plugins and dynamic flows.

Product page: https://cottoncloud.sk/pluginy/custom-performance-cache/#pre-agentury

This document is operational guidance, not a universal performance guarantee. Review date: 2026-09-02.
