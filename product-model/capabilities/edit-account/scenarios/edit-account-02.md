---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit invalid identity or incompatible account selections.",
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
          "place": "gnucash-desktop::account"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Account inputs without accepting the invalid changes.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::account"
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

# Invalid Account

## Trigger

Submit invalid identity or incompatible account selections.

## Outcome

The Product requests corrected Account inputs without accepting the invalid changes.
