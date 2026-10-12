---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "The selected open lots have opposite signs and no suitable existing Transaction links them.",
      "kind": "condition",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::process-payment"
        }
      }
    },
    {
      "text": "Select an unsettled customer Invoice and an unsettled offsetting customer credit note in the same receivable account, enter zero money movement and apply the allocation.",
      "kind": "actor",
      "entities": [
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": [
            "Number",
            "Owner",
            "Outstanding amount"
          ],
          "as": "invoice"
        },
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": [
            "Number",
            "Owner",
            "Outstanding amount"
          ],
          "as": "credit-note"
        },
        {
          "entity": "customer",
          "effect": "reads",
          "facts": [
            "Number",
            "Name"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Name",
            "Type",
            "Commodity"
          ]
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
      "text": "The Product changes Invoice settlement for the selected document and credit note, creates their linking Transaction and dependent Splits, and creates no cash Payment.",
      "kind": "product",
      "entities": [
        {
          "entity": "invoice",
          "effect": "changes",
          "facts": [
            "Outstanding amount",
            "Paid"
          ],
          "as": "invoice"
        },
        {
          "entity": "invoice",
          "effect": "changes",
          "facts": [
            "Outstanding amount",
            "Paid"
          ],
          "as": "credit-note"
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
          "to": "Active"
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
          "entity": "payment",
          "effect": "reads",
          "facts": []
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

# Zero-money document offset

## Trigger

Select offsetting open documents with zero money movement and apply their allocation.

## Outcome

The opposite-sign customer documents are offset without money movement or a cash payment; linking accounting is retained.

## Edge cases

- Vendor bill/credit-note and employee voucher/credit-note offsets use the same owner/account/sign allocation checks and change their corresponding Outstanding amount and Paid facts.
- When a suitable linking transaction already exists, the engine extends it rather than creating another.
- Only open lots in the same account with opposite signs can offset each other.
