---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Delete and decline confirmation.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::saved-report-configurations"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Saved Report Configuration remains unchanged.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "report",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::saved-report-configurations"
        }
      },
      "actor": "user"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-report.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-custom-report.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/report-core.scm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/gnc-report.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-commands.cpp"
    }
  ]
}
---

# Decline removal

## Trigger

Choose Delete and decline confirmation.

## Outcome

The Saved Report Configuration remains unchanged.
