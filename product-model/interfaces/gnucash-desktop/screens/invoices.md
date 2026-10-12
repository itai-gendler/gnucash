---
{
  "entities": [
    {
      "entity": "invoice",
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

# Invoices

Search and read invoice and customer credit-note results.
