---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply a name, recurrence/end condition, template and supported creation settings, then save.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::scheduled-transaction"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product retains the Scheduled Transaction definition and template with initial occurrence progress.",
      "kind": "product",
      "entities": [
        {
          "entity": "scheduled-transaction",
          "effect": "creates",
          "facts": [
            "Name",
            "Enabled",
            "Recurrence",
            "Start",
            "End condition",
            "Automatic creation",
            "Notify",
            "Creation lead days",
            "Reminder lead days",
            "Template content",
            "Last occurrence",
            "Remaining occurrences",
            "Deferred occurrences",
            "Instance count"
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
          "place": "gnucash-desktop::scheduled-transaction"
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

# Save definition/template

## Trigger

Supply a name, recurrence/end condition, template and supported creation settings, then save.

## Outcome

The Product retains the Scheduled Transaction definition and template with initial occurrence progress.
