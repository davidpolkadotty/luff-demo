# LUFF — portfolio demo

Static portfolio version of [LUFF](https://luff.davidppolk.com), an AI-powered
menswear discovery feed that learns your taste. Case study at `/`, live demo at
`/app/`. Fully static — no servers, no accounts; every visitor's taste lives in
their own browser (localStorage).

- `index.html` — the case study
- `app/index.html` — the demo, self-contained: the full product catalog
  (12k+ items, AI style tags) is inlined, and the scene picker, taste
  learning, ranking, search, and infinite feed all run client-side

## Refreshing the catalog

Product data is baked in at build time from the main (private) LUFF repo:

```bash
# in the private luff repo, after a scrape:
python3 personal/build_products.py            # rebuilds personal/index.html with fresh data
# then port the data payload into this repo's app/index.html (the block between
# the PRODUCTS_INLINE markers) and push.
```

Staleness only affects prices/stock display — every "Shop" link goes to the
retailer's live page.

Built by [David Polk](https://davidppolk.com).
