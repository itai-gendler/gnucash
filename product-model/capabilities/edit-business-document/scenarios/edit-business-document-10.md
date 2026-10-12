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
      "text": "Inspect structural-header modification on a posted document or the read-only modifying action.",
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
      "text": "The structural modifying action is disabled or opens the document viewer; Notes/Active callbacks are a distinct metadata route.",
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

# Posted structural-header/read-only action restriction

## Trigger

Inspect structural-header modification on a posted document or the read-only modifying action.

## Outcome

The structural modifying action is disabled or opens the document viewer; Notes/Active callbacks are a distinct metadata route.
