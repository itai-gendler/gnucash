---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Select the vendor, valid posting and transfer accounts, nonzero amount and selected documents, then accept payment.",
      "kind": "actor",
      "entities": [
        {
          "entity": "payment",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "vendor",
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
      "text": "The Product creates the Payment and its accounting Transaction with dependent Splits, allocates money to the selected Bill documents and retains partial outstanding amounts when settlement is incomplete.",
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
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Outstanding amount",
            "Paid"
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

# Vendor payment/partial allocation

## Trigger

Select the vendor, valid posting and transfer accounts, nonzero amount and selected documents, then accept payment.

## Outcome

The Product creates the Payment and its accounting Transaction with dependent Splits, allocates money to the selected Bill documents and retains partial outstanding amounts when settlement is incomplete.
