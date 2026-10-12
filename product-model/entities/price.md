---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-price-editor.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-pricedb.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/app-utils/gnc-quotes.cpp"
    }
  ]
}
---

# Price

A retained dated value for a commodity in a selected currency.

## Information kept

- **Commodity** — The commodity whose price is recorded.
- **Currency** — The currency in which the price is expressed.
- **Date** — The effective date/time of the price.
- **Source** — The source attributed to the price.
- **Type** — The retained price type.
- **Value** — The commodity’s price expressed in the selected currency.
