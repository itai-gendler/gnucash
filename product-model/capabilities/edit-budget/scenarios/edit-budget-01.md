---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Change budget metadata, amounts or notes and record the changes.",
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
      "text": "The Product retains Budget Name, Description, Recurrence, Period count, Account-period amounts and Account-period notes; bulk amount operations follow the selected replace/add/multiply/unset choice.",
      "kind": "product",
      "entities": [
        {
          "entity": "budget",
          "effect": "changes",
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
        },
        {
          "entity": "account",
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

# Metadata, amounts and notes

## Trigger

Change budget metadata, amounts or notes and record the changes.

## Outcome

The Product retains Budget Name, Description, Recurrence, Period count, Account-period amounts and Account-period notes; bulk amount operations follow the selected replace/add/multiply/unset choice.
