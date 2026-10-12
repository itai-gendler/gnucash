---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-scheduled-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::scheduled-transaction"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-scheduled-transaction",
      "contexts": [
        {
          "place": "gnucash-desktop::scheduled-transaction"
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

# Schedule definitions validate templates and warn on ambiguous timing

Validate names/endpoints/accounts and automatic templates; duplicate/never-run cases are warnings, not absolute prohibitions.
