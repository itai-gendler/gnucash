---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Open the schedule list and inspect definitions or upcoming dates.",
      "kind": "actor",
      "entities": [
        {
          "entity": "scheduled-transaction",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::scheduled-transactions"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product presents Scheduled Transaction names, enabled settings, recurrence and next-occurrence information.",
      "kind": "product",
      "entities": [
        {
          "entity": "scheduled-transaction",
          "effect": "reads",
          "facts": [
            "Name",
            "Enabled",
            "Recurrence",
            "Start",
            "End condition",
            "Last occurrence",
            "Remaining occurrences"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::scheduled-transactions"
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

# Definitions and next occurrences

## Trigger

Open Scheduled Transactions and inspect definitions or upcoming dates.

## Outcome

The Product presents Scheduled Transaction names, enabled settings, recurrence and next-occurrence information.
