---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invoice",
      "facts": [
        "Outstanding amount",
        "Paid"
      ]
    },
    {
      "type": "entity",
      "id": "bill",
      "facts": [
        "Outstanding amount",
        "Paid"
      ]
    },
    {
      "type": "entity",
      "id": "expense-voucher",
      "facts": [
        "Outstanding amount",
        "Paid"
      ]
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

# Document paid status derives from posted-lot closure

Paid derives from posted-lot closure; partial/unapplied balances remain possible.
