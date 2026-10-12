---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "voucher-entry",
      "effect": "creates",
      "contexts": [
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
        },
        {
          "fact": "Posted",
          "is": false,
          "entity": "expense-voucher"
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

# Only the User creates ordinary voucher entry records on an unposted document in a writable book

Only the User creates ordinary voucher entry records on an unposted document in a writable book. This governs ordinary document-ledger identity; the related document is the one containing this entry.
