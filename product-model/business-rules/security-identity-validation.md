---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-security",
      "contexts": [
        {
          "place": "gnucash-desktop::securities"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-security",
      "contexts": [
        {
          "place": "gnucash-desktop::securities"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-commodities.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-commodity.cpp"
    }
  ]
}
---

# Custom security identities are required and unique within a namespace

Required identity, collision and reserved-type validation; specialized currency settings remain unmapped.
