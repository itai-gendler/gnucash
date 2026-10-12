---
{
  "entities": [
    {
      "entity": "budget",
      "shows": [
        "Name",
        "Description",
        "Recurrence",
        "Period count",
        "Account-period amounts",
        "Account-period notes"
      ],
      "collects": [
        "Name",
        "Description",
        "Recurrence",
        "Period count",
        "Account-period amounts",
        "Account-period notes"
      ]
    },
    {
      "entity": "account",
      "shows": [
        "Name",
        "Type",
        "Commodity"
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

# Budget

Work with selected budget metadata, periods, amounts and notes, including estimation and bulk inputs.
