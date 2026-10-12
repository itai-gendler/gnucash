---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "budget",
      "effect": "changes",
      "facts": [
        "Account-period amounts",
        "Account-period notes"
      ],
      "contexts": [
        {
          "place": "gnucash-desktop::budget"
        }
      ]
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

# Budget values distinguish unset amounts and apply selected history operations

Blank unsets; invalid expressions are rejected; estimates use selected history/average/precision; bulk changes follow selected operations.
