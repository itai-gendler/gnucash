---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "process-payment",
      "contexts": [
        {
          "place": "gnucash-desktop::process-payment"
        }
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

# Payment allocation validates movement and supports offsets

Validate owner/posting account and nonzero transfer; permit zero offsets and warned unattached payments; conversion cancellation stops application.
