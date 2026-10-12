---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
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
      "actor": "user",
      "capability": "save-report-configuration"
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
      "actor": "user",
      "capability": "save-report-configuration"
    },
    {
      "text": "Supply a nonduplicate name for the selected saved configuration.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::saved-report-configurations"
        }
      },
      "actor": "user",
      "capability": "rename-saved-report-configuration"
    },
    {
      "text": "The Product retains the Saved Report Configuration Name and writes user saved-report configuration data.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "changes",
          "facts": [
            "Name"
          ]
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
      "actor": "user",
      "capability": "rename-saved-report-configuration"
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

New configuration saving opens naming and the user supplies a valid chosen name.

## Outcome

The new Saved Report Configuration retains its chosen nonduplicate Name.
