---
{
  "entities": [
    {
      "entity": "invoice",
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
        "Paid"
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
        "Posting account"
      ]
    },
    {
      "entity": "invoice-entry",
      "shows": [
        "Date",
        "Description",
        "Action",
        "Quantity",
        "Price",
        "Income account",
        "Discount",
        "Discount type",
        "Discount application",
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
        "Income account",
        "Discount",
        "Discount type",
        "Discount application",
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
      "entity": "customer",
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

# Invoice

Work with one document’s header, ordinary entries, totals, posting and payment facts; collect posting inputs in this same context.
