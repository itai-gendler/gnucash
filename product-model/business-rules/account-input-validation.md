---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-account",
      "contexts": [
        {
          "place": "gnucash-desktop::account"
        },
        {
          "place": "gnucash-desktop::account-hierarchy"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-account",
      "contexts": [
        {
          "place": "gnucash-desktop::account"
        },
        {
          "place": "gnucash-desktop::account-hierarchy"
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

# Account inputs pass identity and compatibility validation

Required identity and compatible parent/type/commodity selections pass form validation.
