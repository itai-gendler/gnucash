---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Save As for the working report.",
      "kind": "actor",
      "entities": [
        {
          "entity": "report",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::report"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product creates a separately retained Saved Report Configuration from the Report type/options/embedded configuration, associates it with the working Report and opens naming for the new configuration.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "creates",
          "facts": [
            "Name",
            "Report type",
            "Options",
            "Embedded configurations"
          ]
        },
        {
          "entity": "report",
          "effect": "changes",
          "facts": [
            "Saved configuration"
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

# New configuration

## Trigger

Choose Save As for the working report.

## Outcome

The Product creates a separately retained Saved Report Configuration from the Report type/options/embedded configuration, associates it with the working Report and opens naming for the new configuration.
