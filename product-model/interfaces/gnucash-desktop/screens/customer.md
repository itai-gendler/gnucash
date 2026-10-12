---
{
  "entities": [
    {
      "entity": "customer",
      "shows": [
        "Number",
        "Name",
        "Billing contact",
        "Shipping contact",
        "Active",
        "Currency",
        "Terms",
        "Tax settings",
        "Discount",
        "Credit limit",
        "Notes",
        "Open balance"
      ],
      "collects": [
        "Number",
        "Name",
        "Billing contact",
        "Shipping contact",
        "Active",
        "Currency",
        "Terms",
        "Tax settings",
        "Discount",
        "Credit limit",
        "Notes"
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

# Customer

Work with one customer’s retained contact and accounting settings.
