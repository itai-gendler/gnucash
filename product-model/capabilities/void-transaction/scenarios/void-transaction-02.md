---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Void for cleared, reconciled, already-void or otherwise restricted accounting.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product refuses voiding; the Transaction and Split values remain unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": [
            "Read-only reason"
          ]
        },
        {
          "entity": "split",
          "effect": "reads",
          "facts": [
            "Reconciliation status"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-register.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-split-reg.c#gnc_split_reg_determine_read_only"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/split-register.c#gnc_split_register_save"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Transaction.cpp"
    }
  ]
}
---

# Cleared/reconciled or protected/restricted Transaction

## Trigger

Choose Void for cleared, reconciled, already-void or otherwise restricted accounting.

## Outcome

The Product refuses voiding; the Transaction and Split values remain unchanged.
