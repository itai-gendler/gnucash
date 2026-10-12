---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "security",
      "effect": "removes",
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

# Account references prevent security removal

Account references prevent removal; no universal Transaction-reference check is claimed.
