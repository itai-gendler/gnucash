---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invoice",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::invoice"
        }
      ],
      "to": "Posted"
    },
    {
      "type": "entity",
      "id": "bill",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::bill"
        }
      ],
      "to": "Posted"
    },
    {
      "type": "entity",
      "id": "expense-voucher",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::expense-voucher"
        }
      ],
      "to": "Posted"
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

# Posting requires valid entries and accepted conversions

Require at least one Entry and suitable accounts for nonzero values; cancelled conversion collection leaves Unposted.
