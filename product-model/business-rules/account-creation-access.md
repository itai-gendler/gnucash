---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account",
      "effect": "creates",
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

# Only the User creates accounts through writable accounting entry

Only the User creates accounts through writable accounting entry.
