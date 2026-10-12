---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Since Last Run begins its automatic-creation pass for enabled due Scheduled Transaction occurrences in a writable Book. This pass runs when the process is opened explicitly, or on Book opening with Run schedules on book open enabled in Application Preferences.",
      "kind": "condition",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        },
        {
          "entity": "scheduled-transaction",
          "effect": "reads",
          "facts": [
            "Enabled",
            "Automatic creation",
            "Notify",
            "Template content"
          ]
        },
        {
          "entity": "application-preferences",
          "effect": "reads",
          "facts": [
            "Run schedules on book open"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::since-last-run"
        }
      },
      "unattended": true
    },
    {
      "text": "The Product creates template-derived Active Transactions with dependent Splits, retains the Scheduled Transaction progress and presents automatic-creation notifications according to the definition and startup settings.",
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
      }
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

# Unattended automatic creation

## Trigger

Since Last Run begins its automatic-creation pass for enabled due Scheduled Transaction occurrences in a writable Book. This pass runs when the process is opened explicitly, or on Book opening with Run schedules on book open enabled in Application Preferences.

## Outcome

The Product creates template-derived Active Transactions with dependent Splits, retains the Scheduled Transaction progress and reports notifications according to its setting.
