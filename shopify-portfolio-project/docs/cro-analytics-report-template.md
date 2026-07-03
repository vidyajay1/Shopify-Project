# CRO Report Template (GA4 + Microsoft Clarity)

Fill this in weekly/monthly once the store has real traffic. Structuring it
this way keeps recommendations tied to evidence rather than opinion.

## 1. Headline metrics (GA4)

| Metric | This period | Prior period | Change |
|---|---|---|---|
| Sessions | | | |
| Conversion rate | | | |
| Add-to-cart rate | | | |
| Checkout completion rate | | | |
| Average order value | | | |

## 2. Funnel drop-off (GA4 → Explore → Funnel exploration)

| Step | % of sessions reaching it | Biggest observed drop-off point |
|---|---|---|
| Landing page → PDP | | |
| PDP → Add to cart | | |
| Add to cart → Checkout started | | |
| Checkout started → Purchase | | |

## 3. Behavior signals (Microsoft Clarity)

- **Rage clicks:** pages/elements with unexpected repeated clicks (usually
  signals a non-obvious CTA or a broken interaction)
- **Dead clicks:** elements users click that do nothing (candidate for
  making it an actual link/button)
- **Scroll depth:** % of users reaching key sections (e.g. reviews, size
  guide) — low scroll depth on high-value content = move it up the page
- **Session recordings reviewed:** note 2–3 representative recordings and
  what they revealed

## 4. Hypotheses for this cycle

| Observation | Hypothesis | Proposed test | Priority |
|---|---|---|---|
| e.g. High dead-click rate on badge in `product-card__badge` | Users think the badge is clickable/a filter | Make badge link to a filtered collection, or remove ambiguity in styling | Medium |

## 5. A/B test log

| Test | Page | Variant A | Variant B | Result | Decision |
|---|---|---|---|---|---|
| | | | | | |

## Notes

- Always segment by device (mobile vs. desktop) before drawing conclusions —
  Shopify stores are typically 65-80% mobile traffic and issues often differ
  by device.
- Cross-reference Clarity recordings for any page GA4 flags as an outlier
  before recommending a change — the "why" behind the number matters more
  than the number itself.
