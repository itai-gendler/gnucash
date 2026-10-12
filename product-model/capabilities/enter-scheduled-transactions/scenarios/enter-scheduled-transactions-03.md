---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Ignore for an occurrence and accept processing.",
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
      "text": "The Product advances Scheduled Transaction occurrence progress without creating a Transaction for the ignored occurrence.",
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
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        },
        {
          "entity": "transaction",
          "effect": "reads",
          "facts": []
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

# Ignore occurrence

## Trigger

Choose Ignore for an occurrence and accept processing.

## Outcome

The Product advances Scheduled Transaction occurrence progress without creating a Transaction for the ignored occurrence.
