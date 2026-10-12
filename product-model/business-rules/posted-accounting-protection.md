---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "post-business-document",
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

# Posting retains protected accounting and document associations

Generate entry/tax/posting Splits and retain posting associations/protection.
