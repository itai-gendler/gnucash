---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Choose a new bill, select the named billing owner and supply header facts.",
      "kind": "actor",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user",
      "capability": "create-business-document"
    },
    {
      "text": "The Product creates an Unposted Bill with the selected document type and Number generated when its input is blank, saves the owner-associated header and opens its entry editor.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "creates",
          "facts": [
            "Number",
            "Billing reference",
            "Owner",
            "Opening date",
            "Currency",
            "Terms",
            "Active",
            "Notes",
            "Document type",
            "Posted",
            "Posting date",
            "Due date",
            "Posting account",
            "Posting transaction",
            "Totals",
            "Outstanding amount",
            "Paid",
            "Bill to"
          ],
          "to": "Unposted"
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
      "actor": "user",
      "capability": "create-business-document"
    },
    {
      "text": "Enter valid date, quantity, unit-value and corresponding ledger inputs, then record the row.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user",
      "capability": "add-entry"
    },
    {
      "text": "The Product creates an ordinary Bill Entry under the selected Bill, retains its supported accounting fields and recalculates document totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill-entry",
          "effect": "creates",
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
      "actor": "user",
      "capability": "add-entry"
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
    },
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
    }
  ]
}
---

# Bill

## Trigger

Accepted new-document header saving opens its entry editor, which the user continues.

## Outcome

The selected new unposted document retains a valid ordinary entry.
