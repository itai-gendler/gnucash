---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-business-document",
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
    },
    {
      "type": "capability",
      "id": "edit-business-document",
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

# Business headers require a named end owner and retain generated numbers

Named billing owner is required; blank number is generated; currency follows end owner; document-type changes are limited to new/duplicate forms.
