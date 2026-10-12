---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "invoice",
      "effect": "changes",
      "facts": [
        "Number",
        "Billing reference",
        "Owner",
        "Opening date",
        "Currency",
        "Terms"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::invoice"
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
          "is": false
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

# Only the User edits unposted Invoice structural headers through writable business entry

Only the User edits unposted Invoice structural headers through writable business entry. Structural headers are Number, Billing reference, Owner, Opening date, Currency and Terms, plus subtype facts in the selector. Notes and Active callbacks are outside this structural restriction.
