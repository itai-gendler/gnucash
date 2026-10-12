---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Choose New Budget.",
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
      "actor": "user",
      "capability": "create-budget"
    },
    {
      "text": "The Product creates a default Budget and opens its editor for the next changes.",
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
      "actor": "user",
      "capability": "create-budget"
    },
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
      "actor": "user",
      "capability": "edit-budget"
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
      "actor": "user",
      "capability": "edit-budget"
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

# New Budget

## Trigger

The Product opens the resulting budget editor and the user continues with changes.

## Outcome

The resulting Budget retains the accepted metadata, amounts or notes.
