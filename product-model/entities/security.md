---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-commodity.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-commodities.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-commodity.cpp"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "denominates",
      "cardinality": "one-to-many"
    },
    {
      "entity": "price",
      "verb": "denominates",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Security

A custom security selected through Securities, with independently retained quote settings.

## Information kept

- **Name** — The security’s full displayed name.
- **Namespace** — The security’s namespace.
- **Symbol** — The security symbol within its namespace.
- **Identifier** — The optional identification code.
- **Fraction** — The smallest supported security quantity.
- **User symbol** — The user-selected display symbol.
- **Quote enabled** — Whether online quote retrieval includes the security.
- **Quote source** — The configured Finance::Quote source.
- **Quote timezone** — The timezone selected for quote dating.
