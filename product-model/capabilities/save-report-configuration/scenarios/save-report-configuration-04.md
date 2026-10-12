---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose replacement saving, then decline overwrite confirmation.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::report"
        }
      },
      "actor": "user"
    },
    {
      "text": "The existing Saved Report Configuration remains unchanged; working Report changes are not described as saved.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "reads",
          "facts": [
            "Name",
            "Options"
          ]
        },
        {
          "entity": "report",
          "effect": "reads",
          "facts": [
            "Needs save"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::report"
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

# Decline overwrite

## Trigger

Choose replacement saving, then decline overwrite confirmation.

## Outcome

The existing Saved Report Configuration remains unchanged; working Report changes are not described as saved.
