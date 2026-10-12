---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Void for eligible unreconciled accounting and supply a reason.",
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
      "text": "The Product moves the Transaction from Active to Voided, retains former notes and the void reason/time, protects it and stores former Split amounts/values before setting current amounts/values to zero and status to void.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "changes",
          "facts": [
            "Notes",
            "Former notes",
            "Void reason",
            "Void time",
            "Read-only reason"
          ],
          "from": "Active",
          "to": "Voided"
        },
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Former amount",
            "Former value",
            "Amount",
            "Value",
            "Reconciliation status"
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

# Void and retain former values

## Trigger

Choose Void for eligible unreconciled accounting and supply a reason.

## Outcome

The Product moves the Transaction from Active to Voided, retains former notes and the void reason/time, protects it and stores former Split amounts/values before setting current amounts/values to zero and status to void.
