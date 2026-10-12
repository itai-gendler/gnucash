---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose New, then cancel the unsaved-change prompt.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user"
    },
    {
      "text": "The current Book remains selected with its unsaved contents; replacement stops.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": [
            "Unsaved changes",
            "Location"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/gnc-file.c"
    }
  ]
}
---

# Cancel unsaved-change handling

## Trigger

Choose New, then cancel the unsaved-change prompt.

## Outcome

The current Book remains selected with its unsaved contents; replacement stops.
