---
{
  "entities": [
    {
      "entity": "customer",
      "shows": [
        "Number",
        "Name",
        "Billing contact",
        "Active",
        "Open balance"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-customer.c#gnc_ui_to_customer"
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

# Customers

Read and search customer identities, contact details and unsettled balances.
