---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Name",
        "Code",
        "Description",
        "Notes",
        "Type",
        "Commodity",
        "Precision",
        "Parent",
        "Placeholder",
        "Hidden",
        "Opening balance account",
        "Tax related",
        "Lower balance limit",
        "Upper balance limit",
        "Include subaccounts in balance limits"
      ],
      "collects": [
        "Name",
        "Code",
        "Description",
        "Notes",
        "Type",
        "Commodity",
        "Precision",
        "Parent",
        "Placeholder",
        "Hidden",
        "Opening balance account",
        "Tax related",
        "Lower balance limit",
        "Upper balance limit",
        "Include subaccounts in balance limits"
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

# Account

Work with one selected account’s identity, parent, commodity, precision, flags and limits.
