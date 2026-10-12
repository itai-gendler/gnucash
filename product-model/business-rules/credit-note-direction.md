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

# Credit notes reverse the corresponding document accounting direction

Credit-note cases retain corresponding fact shapes with reversed accounting direction.
