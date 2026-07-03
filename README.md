# Shopify E-Commerce Operations Portfolio

A working Shopify theme project: section/theme editing, landing page
building, metafields & metaobjects, CSS customization, app integration strategy,
and a QA/CRO process.

## What's in here

| Deliverable | File(s) | Skill demonstrated |
|---|---|---|
| Custom landing-page hero section (theme-editor configurable, block-based, like a GemPages/PageFly output) | `sections/hero-landing.liquid` | "Build and optimize landing pages using the Shopify theme editor and third-party apps" |
| Featured collection section pulling metaobject-driven marketing badges | `sections/featured-collection-metaobjects.liquid` | "Manage metafields and metaobjects for products, collections, and pages" |
| Product metafield rendering snippet (size guide, materials, care instructions) | `snippets/product-metafields.liquid` | "Set up products with complete details... manage metafields and metaobjects" |
| JSON template wiring the sections into an actual landing page | `templates/page.landing-page.json` | "Manage and edit Shopify sections, products, collections, and pages" |
| Custom responsive CSS (no framework, mobile-first, uses Shopify CSS custom properties) | `assets/custom-theme.css` | "Apply CSS edits within Shopify's custom code sections" |
| Metafield/metaobject definitions spec | `docs/metafields-metaobjects-setup.md` | Structured data planning |
| App integration plan (email, support, logistics, upsell) | `docs/app-integration-notes.md` | "Integrate and manage various apps across the Shopify ecosystem" |
| Pre/post-launch QA checklist | `docs/qa-checklist.md` | "Conduct QA checks pre and post-launch" |
| GA4 / Clarity CRO report template | `docs/cro-analytics-report-template.md` | "Review Google Analytics and Clarity data to inform CRO improvements" |

## How to actually publish this to a store

You need the Shopify CLI and a development store under your Partner account.

```bash
# 1. Install the CLI (one-time)
npm install -g @shopify/cli @shopify/theme

# 2. From inside this project folder, connect to your Partner org / dev store
shopify theme dev --store your-dev-store.myshopify.com

# 3. When ready, push to the live theme library
shopify theme push --store your-dev-store.myshopify.com
```

This project only contains the custom pieces (sections/snippets/assets/templates) —
it's meant to be dropped into any existing theme (e.g. Dawn) rather than shipped as
a full theme, since that's exactly the kind of scoped work described in the JD
("manage and edit sections," not "build a theme from scratch").

## How to submit

- **GitHub:** `git init && git add . && git commit -m "Shopify portfolio project" && git push`
  — link the repo in your application/portfolio.
- **Shopify Partner dev store:** create a free dev store in Partner Dashboard →
  push this code with the CLI commands above → share the preview link.
