---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "transaction",
      "effect": "creates",
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
          "is": true,
          "entity": "scheduled-transaction"
        },
        {
          "fact": "Automatic creation",
          "is": true,
          "entity": "scheduled-transaction"
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

# The User or enabled automatic processing creates scheduled accounting in a writable book

Manual creation requires the User and a writable book. Unattended creation additionally reads Enabled and Automatic creation on the generating schedule.
