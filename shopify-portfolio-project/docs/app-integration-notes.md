# App Ecosystem Integration Plan

A sample of how I'd approach integrating and managing the categories of apps
called out in the job description, including where they touch the custom
code in this project.

## Landing page builders — GemPages / PageFly

This project uses native Liquid sections instead (`hero-landing.liquid`) to
show the underlying skill, but in a real store I'd choose based on:

- **Native Liquid section** — no app fee, fastest load time, full control;
  best when the design is stable and reused across many pages.
- **GemPages / PageFly** — faster for one-off campaign pages built by
  non-technical marketers, or when a page needs frequent redesigns; costs
  app overhead (extra JS/CSS payload) so I'd audit page speed after each
  major GemPages publish.

## Email marketing (e.g. Klaviyo)

- Add the app's theme app extension block to `templates/page.landing-page.json`
  or product/cart templates rather than hard-coding a script tag, so it stays
  editable from the theme editor and survives theme updates.
- Tag customers/events (viewed product, added to cart, abandoned checkout)
  using the app's native Shopify triggers rather than custom JS where
  possible, to keep tracking reliable across theme changes.

## Customer support (e.g. Gorgias, Zendesk)

- Install as a theme app embed so it can be toggled per-template (e.g. hide
  the chat widget on the checkout page if the plan doesn't include the
  Checkout API) without editing `theme.liquid` directly.

## Logistics / fulfillment (e.g. ShipStation, Shippo)

- These typically don't touch the storefront theme at all — integration
  happens at the order/fulfillment API level. My role would be making sure
  product weight/dimensions metafields (or the native fields) are filled in
  completely, since logistics apps depend on that data for accurate shipping
  rates.

## Upsell / cross-sell apps

- Prefer apps that render via **theme app extension app blocks** (added
  inside `templates/page.landing-page.json`-style JSON templates) over apps
  that inject via `additional_scripts`, since app blocks respect the theme
  editor and are easy to reorder/remove without a developer.

## General principle

Every app added is evaluated for its Lighthouse/page-speed impact before and
after install (see `docs/qa-checklist.md`), since app bloat is one of the
most common causes of CRO regressions on Shopify stores.
