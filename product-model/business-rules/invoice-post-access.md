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
          "state": "Unposted"
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

# Only the User posts an unposted Invoice through writable business entry

Only the User posts an unposted Invoice through writable business entry.
