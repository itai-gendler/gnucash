---
{
  "entities": [
    {
      "entity": "expense-voucher",
      "shows": [
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
      "collects": [
        "Number",
        "Billing reference",
        "Owner",
        "Opening date",
        "Currency",
        "Terms",
        "Active",
        "Notes",
        "Posting date",
        "Due date",
        "Posting account",
        "Charge amount"
      ]
    },
    {
      "entity": "voucher-entry",
      "shows": [
        "Date",
        "Description",
        "Action",
        "Quantity",
        "Price",
        "Expense account",
        "Billable",
        "Payment type",
        "Value"
      ],
      "collects": [
        "Date",
        "Description",
        "Action",
        "Quantity",
        "Price",
        "Expense account",
        "Billable",
        "Payment type"
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
      "entity": "employee",
      "shows": [
        "Number",
        "Username",
        "Payment contact"
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

# Expense Voucher

Work with one document’s header, ordinary entries, totals, posting and payment facts; collect posting inputs in this same context.
