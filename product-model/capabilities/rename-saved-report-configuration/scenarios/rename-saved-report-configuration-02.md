---
{
  "kind": "validation",
  "routes": {
    "main": "GnuCash"
  },
  "steps": [
    {
      "text": "Supply a name already used by another saved configuration.",
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
      "text": "The Product rejects the duplicate Saved Report Configuration Name and asks for another name.",
      "kind": "product",
      "entities": [
        {
          "entity": "saved-report-configuration",
          "effect": "reads",
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

# Duplicate Name

## Trigger

Supply a name already used by another saved configuration.

## Outcome

The Product rejects the duplicate Saved Report Configuration Name and asks for another name.
