---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Name",
        "Code",
        "Description",
        "Type",
        "Commodity",
        "Parent",
        "Hidden",
        "Balance",
        "Cleared balance",
        "Reconciled balance"
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

# Accounts

Search and filter the account hierarchy and balances; supply deletion and reassignment choices here.
