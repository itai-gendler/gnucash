---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit invalid owner/header information in a modifying form.",
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
      "text": "The Product requests corrected Expense Voucher header inputs before accepting the modification.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
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

# Invalid employee header

## Trigger

Submit invalid owner/header information in a modifying form.

## Outcome

The Product requests corrected Expense Voucher header inputs before accepting the modification.
