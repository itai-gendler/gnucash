---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Post before recording any ordinary entries.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product explains that the Invoice requires at least one Entry and leaves it Unposted.",
      "kind": "product",
      "entities": [
        {
          "entity": "invoice",
          "effect": "reads",
          "facts": [
            "Posted"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::invoice"
        }
      },
      "actor": "user"
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

# Empty Invoice

## Trigger

Choose Post before recording any ordinary entries.

## Outcome

The Product reports that the Invoice requires at least one Entry and leaves it Unposted.
