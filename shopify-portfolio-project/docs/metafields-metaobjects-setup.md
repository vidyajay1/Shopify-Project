# Metafields & Metaobjects Setup

Set these up in **Shopify Admin → Settings → Custom data** before the sections
in this project will render fully. This mirrors how you'd scope structured
data for a real merchandising team — defined once, then editable by non-devs
on every product without touching code.

## Metaobject: `promo_badge`

Used by `sections/featured-collection-metaobjects.liquid` to let merchandisers
assign a "Best Seller" / "Limited Restock" style badge from a dropdown.

| Field key | Type | Notes |
|---|---|---|
| `label` | Single line text | e.g. "Best Seller" |
| `color` | Color | Background color of the badge pill |
| `icon` | File (image) | Optional small icon, not currently rendered but reserved for future use |

Then create a **product metafield**:

| Namespace & key | Type | Points to |
|---|---|---|
| `custom.promo_badge` | Metaobject reference | `promo_badge` |

## Metaobject: `size_guide`

Used by `snippets/product-metafields.liquid`.

| Field key | Type |
|---|---|
| `description` | Multi-line text |
| `chart_image` | File (image) |

Product metafield:

| Namespace & key | Type | Points to |
|---|---|---|
| `custom.size_guide` | Metaobject reference | `size_guide` |

## Simple product metafields

| Namespace & key | Type | Used in |
|---|---|---|
| `custom.materials` | Single line text | Product metafields panel |
| `custom.care_instructions` | Multi-line text | Product metafields panel |
| `custom.shipping_note` | Single line text | Product metafields panel |
| `custom.material` | Single line text | Featured collection product card (short badge under title) |

## Why this structure

- **Metaobjects** are used where the *same* structured entry (a badge, a size
  chart) needs to be reused across many products without re-typing it — edit
  once, updates everywhere it's referenced.
- **Simple metafields** are used where the value is genuinely per-product
  (materials, care instructions).
- Everything is under the `custom` namespace to avoid collisions with
  app-installed metafields (e.g. from review or bundle apps).
