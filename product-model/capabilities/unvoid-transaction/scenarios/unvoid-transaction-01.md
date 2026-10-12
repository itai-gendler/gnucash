---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Unvoid for an eligible voided transaction.",
      "kind": "actor",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product restores the Transaction to Active, restores former notes, clears void/protection facts and restores each Split’s former amounts/values with unreconciled status.",
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
          "from": "Voided",
          "to": "Active"
        },
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Amount",
            "Value",
            "Former amount",
            "Former value",
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

# Restore values with unreconciled indicators

## Trigger

Choose Unvoid for an eligible voided transaction.

## Outcome

The Product restores the Transaction to Active, restores former notes, clears void/protection facts and restores each Split’s former amounts/values with unreconciled status.
