# Pre/Post-Launch QA Checklist

Used before pushing any theme change (new section, CSS edit, app install) live.

## Pre-launch (on a theme preview / duplicate theme)

- [ ] Test on a duplicate theme, never edit the live theme directly
- [ ] Check layout at 375px, 768px, 1024px, 1440px widths
- [ ] Test in Safari (iOS) and Chrome (Android) at minimum — Safari flexbox/gap
      bugs are common
- [ ] Verify all metafield-driven content degrades gracefully when the field
      is empty (no broken layout, no "undefined" text)
- [ ] Run Lighthouse (mobile) before and after the change — flag anything
      that drops Performance score by more than 5 points
- [ ] Check that new sections/blocks respect the theme editor: settings save
      correctly, presets work, blocks reorder without breaking layout
- [ ] Validate all links (CTA buttons, collection links) resolve, not `#`
- [ ] Confirm images have descriptive alt text (SEO + accessibility)
- [ ] Check color contrast on any custom text/background combos (WCAG AA)

## Post-launch (on the live site)

- [ ] Full click-through of the changed page/flow on live, not preview
- [ ] Confirm Google Analytics / GA4 is still firing (check Realtime report)
- [ ] Confirm Microsoft Clarity recording is still active on the page
- [ ] Check page speed on live (apps can behave differently once live vs.
      preview due to CDN caching)
- [ ] Spot-check checkout flow if the change touched cart/product templates
- [ ] Monitor for 24–48 hours: bounce rate, conversion rate, and any spike in
      support tickets referencing the changed page

## Rollback plan

Keep the previous theme version published as a backup, or use Shopify's
theme version history, so any regression can be reverted in under a minute
rather than debugged live under pressure.
