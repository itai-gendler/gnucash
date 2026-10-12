---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-budget",
      "contexts": [
        {
          "place": "gnucash-desktop::budget"
        }
      ]
    },
    {
      "type": "capability",
      "id": "copy-budget",
      "contexts": [
        {
          "place": "gnucash-desktop::budget"
        }
      ]
    },
    {
      "type": "capability",
      "id": "open-budget",
      "contexts": [
        {
          "place": "gnucash-desktop::budget"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-budget.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-budget.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-budget-view.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-budget.cpp"
    }
  ]
}
---

# Budget creation follows the inspected entry route

New/Copy actions have read-only gates; Open’s empty-collection fallback invokes creation without the equivalent gate.
