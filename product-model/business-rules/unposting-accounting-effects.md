---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "unpost-business-document",
      "contexts": [
        {
          "place": "gnucash-desktop::invoice"
        },
        {
          "place": "gnucash-desktop::bill"
        },
        {
          "place": "gnucash-desktop::expense-voucher"
        }
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

# Unposting removes posting accounting and adjusts settlement links

Remove posting, reset associations, detach/rebalance settlement links, optionally reset tax tables; do not promise deletion of payments.
