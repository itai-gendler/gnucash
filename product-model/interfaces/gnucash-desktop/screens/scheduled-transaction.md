---
{
  "entities": [
    {
      "entity": "scheduled-transaction",
      "shows": [
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
        "Remaining occurrences"
      ],
      "collects": [
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
        "Last occurrence"
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

# Scheduled Transaction

Work with one schedule definition and its accounting template.
