---
{
  "kind": "validation",
  "routes": {
    "invoice": "Invoice",
    "bill": "Bill",
    "expense-voucher": "Expense Voucher"
  },
  "steps": [
    {
      "text": "Inspect new business-document actions in a read-only session.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "invoice": {
          "place": "gnucash-desktop::invoice"
        },
        "bill": {
          "place": "gnucash-desktop::bill"
        },
        "expense-voucher": {
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user"
    },
    {
      "text": "The creation actions are disabled; no document is created.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        }
      ],
      "contexts": {
        "invoice": {
          "place": "gnucash-desktop::invoice"
        },
        "bill": {
          "place": "gnucash-desktop::bill"
        },
        "expense-voucher": {
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

# Read-only creation action

## Trigger

Inspect new business-document actions in a read-only session.

## Outcome

The creation actions are disabled; no document is created.
