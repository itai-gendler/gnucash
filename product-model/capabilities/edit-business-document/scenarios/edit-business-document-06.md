---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change Notes or Active through the posted document’s metadata callbacks.",
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
      "text": "The Product retains the posted Expense Voucher Notes/Active changes while preserving its posting accounting and structural header.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
          "effect": "changes",
          "facts": [
            "Notes",
            "Active"
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

# Posted Voucher Notes/Active metadata

## Trigger

Change Notes or Active through the posted document’s metadata callbacks.

## Outcome

The Product retains the posted Expense Voucher Notes/Active changes while preserving its posting accounting and structural header.
