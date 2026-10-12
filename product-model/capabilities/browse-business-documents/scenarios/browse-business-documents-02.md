---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Search documents using owner, number, dates or posting/settlement criteria.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bills"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents Bill and corresponding credit-note results with posting, totals and settlement facts.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": [
            "Number",
            "Owner",
            "Opening date",
            "Due date",
            "Document type",
            "Posted",
            "Totals",
            "Outstanding amount",
            "Paid"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bills"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-invoice.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-invoice.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncInvoice.c"
    }
  ]
}
---

# Bills/credit notes

## Trigger

Search documents using owner, number, dates or posting/payment criteria.

## Outcome

The Product presents Bill and corresponding credit-note results with posting, totals and settlement facts.
