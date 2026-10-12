---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "customer",
      "facts": [
        "Discount",
        "Credit limit"
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

# Customer discount and credit amounts pass form validation

Customer form discount is blank or a valid percentage from 0 to 100; credit limit is blank or a valid nonnegative amount in customer currency. These values do not establish invoice credit-limit enforcement.
