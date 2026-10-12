---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Post before recording any ordinary entries.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product explains that the Expense Voucher requires at least one Entry and leaves it Unposted.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
          "effect": "reads",
          "facts": [
            "Posted"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::expense-voucher"
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

# Empty Voucher

## Trigger

Choose Post before recording any ordinary entries.

## Outcome

The Product reports that the Expense Voucher requires at least one Entry and leaves it Unposted.
