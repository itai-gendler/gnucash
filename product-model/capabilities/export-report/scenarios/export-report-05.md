---
{
  "kind": "edge",
  "routes": {
    "main": "GnuCash CLI"
  },
  "steps": [
    {
      "text": "Export when rendering/exporting fails or the output destination cannot be opened.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
        }
      },
      "actor": "user"
    },
    {
      "text": "The Product displays diagnostics for exporter or destination failure; the output-file-open diagnostic path can leave command exit status zero, so diagnostics and output must be observed.",
      "kind": "product",
      "entities": [
        {
          "entity": "report",
          "effect": "reads",
          "facts": [
            "Rendered content"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-cli"
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

# Exporter/destination failure in GnuCash CLI

## Trigger

Export when rendering/exporting fails or the output destination cannot be opened.

## Outcome

The Product reports exporter or destination failure; the output-file-open diagnostic path can leave command exit status zero, so diagnostics and output must be observed.
