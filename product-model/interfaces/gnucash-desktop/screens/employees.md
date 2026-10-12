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
        "Open balance"
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

# Employees

Read and search employee identities, contact details and unsettled balances.
