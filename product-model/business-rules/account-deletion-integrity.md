---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-account",
      "contexts": [
        {
          "place": "gnucash-desktop::accounts"
        }
      ]
    },
    {
      "type": "entity",
      "id": "account",
      "effect": "removes",
      "contexts": [
        {
          "place": "gnucash-desktop::accounts"
        }
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

# Account deletion honors protected accounting and reassignment choices

Reassignment/destruction follows selected choices; protected destructive choices are disabled; commodity mismatches require confirmation.
