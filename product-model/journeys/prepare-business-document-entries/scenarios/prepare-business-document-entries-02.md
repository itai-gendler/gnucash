---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Choose a new customer credit note, select the named billing owner and supply header facts.",
      "kind": "actor",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user",
      "capability": "create-business-document"
    },
    {
      "text": "The Product creates an Unposted Invoice with the selected document type and Number generated when its input is blank, saves the owner-associated header and opens its entry editor.",
      "kind": "product",
      "entities": [
        {
          "entity": "invoice",
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
            "Paid"
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
          "place": "gnucash-desktop::invoice"
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
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user",
      "capability": "add-entry"
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

# Customer credit note

## Trigger

Accepted new-document header saving opens its entry editor, which the user continues.

## Outcome

The selected new unposted document retains a valid ordinary entry.
