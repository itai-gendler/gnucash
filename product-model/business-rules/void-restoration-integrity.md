---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ],
      "to": "Voided"
    },
    {
      "type": "entity",
      "id": "transaction",
      "effect": "changes",
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ],
      "to": "Active"
    },
    {
      "type": "entity",
      "id": "split",
      "effect": "changes",
      "facts": [
        "Former amount",
        "Former value",
        "Amount",
        "Value",
        "Reconciliation status"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::register"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Transaction.cpp#xaccTransVoid"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Transaction.cpp#xaccTransUnvoid"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Split.cpp#xaccSplitUnvoid"
    }
  ]
}
---

# Voiding and restoration preserve former accounting values

Voiding refuses cleared/reconciled Splits, retains former values/notes, zeroes values and marks void; unvoid restores values and unreconciled status.
