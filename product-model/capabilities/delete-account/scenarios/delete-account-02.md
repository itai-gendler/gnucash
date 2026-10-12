---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Delete, select replacement accounts for children and accounting, and confirm.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [],
          "as": "selected-account"
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::accounts"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product reassigns child Accounts and affected Splits according to the accepted choices, then removes the selected Account.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Parent"
          ],
          "as": "child-account"
        },
        {
          "entity": "account",
          "effect": "removes",
          "as": "selected-account"
        },
        {
          "entity": "split",
          "effect": "changes",
          "facts": [
            "Account"
          ]
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::accounts"
        }
      },
      "actor": "user"
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

# Reassign children/Transactions and remove Account

## Trigger

Choose Delete, select replacement accounts for children and accounting, and confirm.

## Outcome

The Product reassigns child Accounts and affected Splits according to the accepted choices, then removes the selected Account.
