---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Apply a nonzero amount with valid accounts but no selected document, accepting the warning about an unallocated amount.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::process-payment"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates the Payment and its accounting Transaction with dependent Splits and retains an unapplied amount for future settlement.",
      "kind": "product",
      "entities": [
        {
          "entity": "payment",
          "effect": "creates",
          "facts": [
            "Company",
            "Date",
            "Number",
            "Memo",
            "Amount",
            "Posting account",
            "Transfer account",
            "Document allocations",
            "Unapplied amount",
            "Accounting transaction"
          ]
        },
        {
          "entity": "transaction",
          "effect": "creates",
          "facts": [
            "Posted date",
            "Entered date",
            "Number",
            "Description",
            "Notes",
            "Currency",
            "Read-only reason",
            "Void reason",
            "Void time",
            "Former notes",
            "Reversing transaction",
            "Scheduled source",
            "Document link"
          ],
          "to": "Active",
          "with": "payment"
        },
        {
          "entity": "split",
          "effect": "creates",
          "facts": [
            "Account",
            "Memo",
            "Action",
            "Amount",
            "Value",
            "Reconciliation status",
            "Reconciliation date",
            "Former amount",
            "Former value",
            "Online identifier"
          ],
          "with": "transaction"
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
          "place": "gnucash-desktop::process-payment"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-payment.c#gnc_payment_window_check_payment"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-payment.c#gnc_payment_ok_cb"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncOwner.c#gncOwnerApplyPaymentSecs"
    }
  ]
}
---

# Unattached payment

## Trigger

Apply a nonzero amount with valid accounts but no selected document, accepting the unattached-payment warning.

## Outcome

The Product creates the Payment and its accounting Transaction with dependent Splits and retains an unapplied amount for future settlement.
