---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Enter valid date, quantity, unit-value and corresponding ledger inputs, then record the row.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates an ordinary Invoice Entry under the selected Invoice, retains its supported accounting fields and recalculates document totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "invoice-entry",
          "effect": "creates",
          "facts": [
            "Date",
            "Description",
            "Action",
            "Quantity",
            "Price",
            "Income account",
            "Discount",
            "Discount type",
            "Discount application",
            "Taxable",
            "Tax included",
            "Tax table",
            "Value",
            "Tax value"
          ]
        },
        {
          "entity": "invoice",
          "effect": "changes",
          "facts": [
            "Totals"
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
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerControl.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerModel.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerLayout.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-invoice.cpp"
    }
  ]
}
---

# Invoice Entry

## Trigger

Enter valid dated quantity, price and corresponding ledger fields, then record the row.

## Outcome

The Product creates an ordinary Invoice Entry under the selected Invoice, retains its supported accounting fields and recalculates document totals.
