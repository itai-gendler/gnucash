---
{
  "entities": [
    {
      "entity": "payment",
      "shows": [
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
      ],
      "collects": [
        "Company",
        "Date",
        "Number",
        "Memo",
        "Amount",
        "Posting account",
        "Transfer account",
        "Document allocations"
      ]
    },
    {
      "entity": "invoice",
      "shows": [
        "Number",
        "Owner",
        "Outstanding amount",
        "Paid"
      ]
    },
    {
      "entity": "bill",
      "shows": [
        "Number",
        "Owner",
        "Outstanding amount",
        "Paid"
      ]
    },
    {
      "entity": "expense-voucher",
      "shows": [
        "Number",
        "Owner",
        "Outstanding amount",
        "Paid"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Type",
        "Commodity"
      ]
    },
    {
      "entity": "customer",
      "shows": [
        "Number",
        "Name"
      ]
    },
    {
      "entity": "vendor",
      "shows": [
        "Number",
        "Name"
      ]
    },
    {
      "entity": "employee",
      "shows": [
        "Number",
        "Payment contact"
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

# Process Payment

Select company, movement, accounts and allocations; inspect remaining settlement amounts.
