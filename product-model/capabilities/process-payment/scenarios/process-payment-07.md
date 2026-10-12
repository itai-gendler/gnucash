---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Inspect Process Payment from the read-only business entry action.",
      "kind": "actor",
      "entities": [
        {
          "entity": "payment",
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
      "text": "The entry action is disabled and no Payment or settlement is applied.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        },
        {
          "entity": "payment",
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

# Read-only business entry action

## Trigger

Inspect Process Payment from the read-only business entry action.

## Outcome

The entry action is disabled and no Payment or settlement is applied.
