---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "creates",
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
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
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

# Only the User creates document posting accounting through writable business entry

Only the User creates document posting accounting through writable business entry.
