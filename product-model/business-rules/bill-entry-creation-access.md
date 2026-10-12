---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "bill-entry",
      "effect": "creates",
      "contexts": [
        {
          "place": "gnucash-desktop::bill"
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
          "entity": "bill"
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

# Only the User creates ordinary bill entry records on an unposted document in a writable book

Only the User creates ordinary bill entry records on an unposted document in a writable book. This governs ordinary document-ledger identity; the related document is the one containing this entry.
