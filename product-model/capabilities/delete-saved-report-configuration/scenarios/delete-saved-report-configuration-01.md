---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Delete for a saved configuration and confirm.",
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
      "text": "The Product removes the Saved Report Configuration and writes updated user configuration data.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "removes"
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

# Confirmed removal

## Trigger

Choose Delete for a saved configuration and confirm.

## Outcome

The Product removes the Saved Report Configuration and writes updated user configuration data.
