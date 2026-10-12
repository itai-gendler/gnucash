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
      "text": "Inspect Post on an already posted document or in a read-only session.",
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
      "text": "The posting action is disabled; no second posting is created.",
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

# Posted/read-only action

## Trigger

Inspect Post on an already posted document or in a read-only session.

## Outcome

The posting action is disabled; no second posting is created.
