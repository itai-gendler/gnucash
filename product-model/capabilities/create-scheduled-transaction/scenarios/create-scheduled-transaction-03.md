---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a duplicate name or a definition with no future occurrence, then accept its warning.",
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
      "text": "The Product retains the Scheduled Transaction definition and template after the warning is accepted.",
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

# Duplicate-name or never-run warning choice

## Trigger

Submit a duplicate name or a definition with no future occurrence, then respond to the warning.

## Outcome

The warning is observable and acceptance retains the definition; it is not an absolute name/timing prohibition.

## Edge cases

- Declining the warning returns to correction without accepted definition saving.
