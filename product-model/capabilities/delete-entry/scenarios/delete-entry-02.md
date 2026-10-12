---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Delete for the selected ordinary ledger row.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::bill"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product removes the Bill Entry from the ordinary Bill ledger and recalculates its totals.",
      "kind": "product",
      "entities": [
        {
          "entity": "bill-entry",
          "effect": "removes"
        },
        {
          "entity": "bill",
          "effect": "changes",
          "facts": [
            "Totals"
          ]
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
      "target": "gnucash/register/ledger-core/gncEntryLedgerControl.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerModel.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerLayout.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-invoice.cpp"
    }
  ]
}
---

# Bill Entry

## Trigger

Choose Delete for the selected ordinary ledger row.

## Outcome

The Product removes the Bill Entry from the ordinary Bill ledger and recalculates its totals.
