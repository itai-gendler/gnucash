---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose a new bill, select the named billing owner and supply header facts.",
      "kind": "actor",
      "entities": [
        {
          "entity": "bill",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates an Unposted Bill with the selected document type and Number generated when its input is blank, saves the owner-associated header and opens its entry editor.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill",
          "effect": "creates",
          "facts": [
            "Number",
            "Billing reference",
            "Owner",
            "Opening date",
            "Currency",
            "Terms",
            "Active",
            "Notes",
            "Document type",
            "Posted",
            "Posting date",
            "Due date",
            "Posting account",
            "Posting transaction",
            "Totals",
            "Outstanding amount",
            "Paid",
            "Bill to"
          ],
          "to": "Unposted"
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
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

# Bill

## Trigger

Choose a new bill, select the named billing owner and supply header facts.

## Outcome

The Product creates an Unposted Bill with the selected document type and Number generated when its input is blank, saves the owner-associated header and opens its entry editor.
