---
{
  "entities": [
    {
      "entity": "expense-voucher",
      "shows": [
        "Number",
        "Owner",
        "Opening date",
        "Due date",
        "Active",
        "Document type",
        "Posted",
        "Totals",
        "Outstanding amount",
        "Paid"
      ]
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
    }
  ]
}
---

# Expense Vouchers

Search and read voucher and employee credit-note results.
