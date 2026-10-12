---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change a selected ordinary entry’s supported accounting fields and record the row.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product retains the Bill Entry changes and recalculates the Bill totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill-entry",
          "effect": "changes",
          "facts": [
            "Date",
            "Description",
            "Action",
            "Quantity",
            "Price",
            "Expense account",
            "Billable",
            "Taxable",
            "Tax included",
            "Tax table",
            "Value",
            "Tax value"
          ]
        },
        {
          "entity": "bill",
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
          "place": "gnucash-desktop::bill"
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

# Bill Entry

## Trigger

Change a selected ordinary entry’s supported accounting fields and record the row.

## Outcome

The Product retains the Bill Entry changes and recalculates the Bill totals.
