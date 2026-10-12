---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invoice",
      "facts": [
        "Posting account",
        "Currency"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::invoice"
        }
      ]
    },
    {
      "type": "entity",
      "id": "bill",
      "facts": [
        "Posting account",
        "Currency"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::bill"
        }
      ]
    },
    {
      "type": "entity",
      "id": "expense-voucher",
      "facts": [
        "Posting account",
        "Currency"
      ],
      "contexts": [
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

# Posting accounts and currency follow the document owner

Customer uses receivable; vendor/employee use payable; owner currency and collected conversions govern posting.
