---
{
  "entities": [
    {
      "entity": "employee",
      "shows": [
        "Number",
        "Username",
        "Payment contact",
        "Active",
        "Language",
        "Workday",
        "Rate",
        "Currency",
        "Credit-card account",
        "Open balance"
      ],
      "collects": [
        "Number",
        "Username",
        "Payment contact",
        "Active",
        "Language",
        "Workday",
        "Rate",
        "Currency",
        "Credit-card account"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-employee.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-owner-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-business.c"
    }
  ]
}
---

# Employee

Work with one employee’s contact and payment settings.
