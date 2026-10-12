---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Process occurrences whose formula or accounting generation encounters errors.",
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
      "text": "The Product displays diagnostics for creation errors and successful results separately; it does not guarantee all-or-nothing Transaction generation or occurrence progress.",
      "kind": "product",
      "entities": [
        {
          "entity": "scheduled-transaction",
          "effect": "reads",
          "facts": [
            "Last occurrence",
            "Remaining occurrences",
            "Deferred occurrences",
            "Instance count"
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

# Report creation errors

## Trigger

Process occurrences whose formula or accounting generation encounters errors.

## Outcome

The Product reports creation errors and successful results separately; it does not guarantee all-or-nothing Transaction generation or occurrence progress.
