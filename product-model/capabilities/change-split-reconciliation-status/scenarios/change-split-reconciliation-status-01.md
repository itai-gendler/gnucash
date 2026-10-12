---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose the next supported reconciliation indicator for a selected split and accept any required warning.",
      "kind": "actor",
      "entities": [
        {
          "entity": "split",
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
      "text": "The Product retains the Split reconciliation status; accepting an unreconcile change removes the reconciled indicator.",
      "kind": "product",
      "entities": [
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
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

# Change indicator

## Trigger

Choose the next supported reconciliation indicator for a selected split and accept any required warning.

## Outcome

The Product retains the Split reconciliation status; accepting an unreconcile change removes the reconciled indicator.
