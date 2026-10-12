---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose creation for a due occurrence, bind required variables and accept processing.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::since-last-run"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product evaluates template formulas and accepted bindings, creates linked Active Transactions with dependent Splits, and advances Scheduled Transaction progress for successful creation. With review of created results selected, the Product opens their Register.",
      "kind": "product",
      "entities": [
        {
          "entity": "scheduled-transaction",
          "effect": "changes",
          "facts": [
            "Last occurrence",
            "Remaining occurrences",
            "Deferred occurrences",
            "Instance count"
          ]
        },
        {
          "entity": "transaction",
          "effect": "creates",
          "facts": [
            "Posted date",
            "Entered date",
            "Number",
            "Description",
            "Notes",
            "Currency",
            "Read-only reason",
            "Void reason",
            "Void time",
            "Former notes",
            "Reversing transaction",
            "Scheduled source",
            "Document link"
          ],
          "to": "Active"
        },
        {
          "entity": "split",
          "effect": "creates",
          "facts": [
            "Account",
            "Memo",
            "Action",
            "Amount",
            "Value",
            "Reconciliation status",
            "Reconciliation date",
            "Former amount",
            "Former value",
            "Online identifier"
          ],
          "with": "transaction"
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
          "place": "gnucash-desktop::since-last-run"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-sx-list.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-sx-editor.c#gnc_sxed_save_sx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-sx-since-last-run.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/app-utils/gnc-sx-instance-model.c#gnc_sx_instance_model_effect_change"
    }
  ]
}
---

# Manual creation

## Trigger

Choose creation for a due occurrence, bind required variables and accept processing.

## Outcome

The Product evaluates template formulas and accepted bindings, creates linked Active Transactions with dependent Splits, and advances Scheduled Transaction progress for successful creation.
