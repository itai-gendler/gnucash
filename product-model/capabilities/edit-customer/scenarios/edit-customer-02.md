---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Submit a blank company name, a discount outside 0–100, an invalid amount or a negative credit limit while editing.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::customer"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product requests corrected Customer inputs and leaves the invalid form changes unaccepted.",
      "kind": "product",
      "entities": [
        {
          "entity": "customer",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::customer"
        }
      },
      "actor": "user"
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

# Invalid facts

## Trigger

Submit a blank company name, a discount outside 0–100, an invalid amount or a negative credit limit while editing.

## Outcome

The Product requests corrected Customer inputs and leaves the invalid form changes unaccepted.
