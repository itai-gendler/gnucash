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
      "to": "Unposted"
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
          "state": "Posted"
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

# Only the User unposts a posted Invoice through writable business entry

Only the User unposts a posted Invoice through writable business entry.
