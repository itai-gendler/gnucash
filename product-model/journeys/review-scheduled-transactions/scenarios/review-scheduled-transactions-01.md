---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
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
      "actor": "user",
      "capability": "enter-scheduled-transactions"
    },
    {
      "text": "The Product evaluates template formulas and accepted bindings, creates linked Active Transactions with dependent Splits, and advances Scheduled Transaction progress for successful creation. With review selected, the Product opens the generated-result Register.",
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
      "actor": "user",
      "capability": "enter-scheduled-transactions"
    },
    {
      "text": "Open the account register or a filtered accounting search.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user",
      "capability": "browse-transactions"
    },
    {
      "text": "The Product presents the selected Transaction/Split accounting and Account balances without posting changes.",
      "kind": "product",
      "entities": [
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": [
            "Posted date",
            "Number",
            "Description",
            "Notes",
            "Currency"
          ]
        },
        {
          "entity": "split",
          "effect": "reads",
          "facts": [
            "Account",
            "Memo",
            "Action",
            "Amount",
            "Value",
            "Reconciliation status",
            "Reconciliation date"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Balance",
            "Cleared balance",
            "Reconciled balance"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::register"
        }
      },
      "actor": "user",
      "capability": "browse-transactions"
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
    },
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

# Created transactions with review selected

## Trigger

Successful scheduled creation runs with review of created transactions selected.

## Outcome

The generated Transaction results are presented in the Register.
