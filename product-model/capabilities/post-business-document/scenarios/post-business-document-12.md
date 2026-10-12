---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Post with pending Notes/Active edits for the unposted document.",
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
      "text": "Before collecting conversions, the Product saves the Expense Voucher Notes and Active metadata, including Charge amount and sets Currency from its owner.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
          "effect": "changes",
          "facts": [
            "Notes",
            "Active",
            "Currency",
            "Charge amount"
          ]
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user"
    },
    {
      "text": "Cancel the required foreign-currency conversion collection.",
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
      "text": "Cancelling conversion collection leaves it Unposted and creates no posting Transaction; the earlier metadata save remains.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
          "effect": "reads",
          "facts": [
            "Posted"
          ]
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
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

# Cancel Voucher conversions

## Trigger

Choose Post with pending Notes/Active edits, then cancel the required foreign-currency conversion collection.

## Outcome

Before collecting conversions, the Product saves the Expense Voucher Notes and Active metadata, including Charge amount and sets Currency from its owner. Cancelling conversion collection leaves it Unposted and creates no posting Transaction; the earlier metadata save remains.
