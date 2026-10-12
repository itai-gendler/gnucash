---
{
  "kind": "primary",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Choose Save for a report with an existing saved configuration and accept replacement.",
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
      "text": "The Product replaces the Saved Report Configuration’s type/options/embedded configuration while retaining its identity and updates the working Report’s saved association.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "changes",
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

# Replace existing configuration

## Trigger

Choose Save for a report with an existing saved configuration and accept replacement.

## Outcome

The Product replaces the Saved Report Configuration’s type/options/embedded configuration while retaining its identity and updates the working Report’s saved association.
