---
{
  "entities": [
    {
      "entity": "bill",
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
        "Bill to"
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
        "Bill to"
      ]
    },
    {
      "entity": "bill-entry",
      "shows": [
        "Date",
        "Description",
        "Action",
        "Quantity",
        "Price",
        "Expense account",
        "Billable",
        "Taxable",
        "Tax included",
        "Tax table",
        "Value",
        "Tax value"
      ],
      "collects": [
        "Date",
        "Description",
        "Action",
        "Quantity",
        "Price",
        "Expense account",
        "Billable",
        "Taxable",
        "Tax included",
        "Tax table"
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
      "entity": "vendor",
      "shows": [
        "Number",
        "Name"
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

# Bill

Work with one document’s header, ordinary entries, totals, posting and payment facts; collect posting inputs in this same context.
