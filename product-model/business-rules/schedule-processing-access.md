---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "scheduled-transaction",
      "effect": "changes",
      "facts": [
        "Last occurrence",
        "Remaining occurrences",
        "Deferred occurrences",
        "Instance count"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::since-last-run"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "user"
      ],
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
        }
      ]
    },
    {
      "unattended": true,
      "when": [
        {
          "fact": "Session access",
          "is": "Writable",
          "entity": "book"
        },
        {
          "fact": "Enabled",
          "is": true
        },
        {
          "fact": "Automatic creation",
          "is": true
        }
      ]
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

# The User or enabled automatic processing advances schedules in a writable book

The User can process progress in a writable book. Unattended processing additionally requires Enabled and Automatic creation on the source definition.
