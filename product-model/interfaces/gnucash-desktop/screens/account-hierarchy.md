---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Name",
        "Description",
        "Type",
        "Commodity",
        "Parent"
      ],
      "collects": [
        "Name",
        "Commodity"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-account-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-account.c#gnc_ui_to_account"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/assistant-hierarchy.cpp#on_finish"
    }
  ]
}
---

# Account Hierarchy

Choose template accounts and opening-balance inputs in one hierarchy-creation process.
