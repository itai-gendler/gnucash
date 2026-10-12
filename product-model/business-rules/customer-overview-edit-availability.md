---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-customer",
      "contexts": [
        {
          "place": "gnucash-desktop::customers"
        }
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

# Customer overview editing has a read-only action gate

Overview editing has its inspected read-only gate; no universal dialog policy is asserted.
