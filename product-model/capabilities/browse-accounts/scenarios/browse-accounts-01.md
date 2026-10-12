---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Open Accounts and supply optional search or filter choices.",
      "kind": "actor",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
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
      "text": "The Product presents Account hierarchy, identities, commodities and derived balances for the selected scope.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
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

# Show/search hierarchy and balances

## Trigger

Open Accounts and supply optional search or filter choices.

## Outcome

The Product presents Account hierarchy, identities, commodities and derived balances for the selected scope.
