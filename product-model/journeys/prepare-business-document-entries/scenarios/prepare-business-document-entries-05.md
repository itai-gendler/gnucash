---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Choose a new expense voucher, select the named billing owner and supply header facts.",
      "kind": "actor",
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
      "actor": "user",
      "capability": "create-business-document"
    },
    {
      "text": "The Product creates an Unposted Expense Voucher with the selected document type and Number generated when its input is blank, saves the owner-associated header and opens its entry editor.",
      "kind": "product",
      "entities": [
        {
          "entity": "expense-voucher",
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
            "Charge amount"
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
          "place": "gnucash-desktop::expense-voucher"
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
          "place": "gnucash-desktop::expense-voucher"
        }
      },
      "actor": "user",
      "capability": "add-entry"
    },
    {
      "text": "The Product creates an ordinary Voucher Entry under the selected Expense Voucher, retains its supported accounting fields and recalculates document totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "voucher-entry",
          "effect": "creates",
          "facts": [
            "Date",
            "Description",
            "Action",
            "Quantity",
            "Price",
            "Expense account",
            "Billable",
            "Payment type",
            "Value"
          ]
        },
        {
          "entity": "expense-voucher",
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
          "place": "gnucash-desktop::expense-voucher"
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

# Voucher

## Trigger

Accepted new-document header saving opens its entry editor, which the user continues.

## Outcome

The selected new unposted document retains a valid ordinary entry.
