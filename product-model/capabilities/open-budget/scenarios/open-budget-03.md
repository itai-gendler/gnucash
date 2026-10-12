---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Open Budget in a read-only session whose budget collection is empty.",
      "kind": "actor",
      "entities": [
        {
          "entity": "budget",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::budget"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Book is Read-only and its Budget collection is empty.",
      "kind": "condition",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Session access"
          ]
        },
        {
          "entity": "budget",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::budget"
        }
      }
    },
    {
      "text": "The Product still enters its empty-collection creation fallback and opens a default Budget in memory; editing actions remain restricted and the read-only Book source is not thereby persisted.",
      "kind": "product",
      "entities": [
        {
          "entity": "budget",
          "effect": "creates",
          "facts": [
            "Name",
            "Description",
            "Recurrence",
            "Period count",
            "Account-period amounts",
            "Account-period notes"
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
          "place": "gnucash-desktop::budget"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-budget.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-budget.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-budget-view.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-budget.cpp"
    }
  ]
}
---

# Read-only empty collection still enters creation fallback, while editing/persistence restrictions remain

## Trigger

Choose Open Budget in a read-only session whose budget collection is empty.

## Outcome

The Product still enters its empty-collection creation fallback and opens a default Budget in memory; editing actions remain restricted and the read-only Book source is not thereby persisted.
