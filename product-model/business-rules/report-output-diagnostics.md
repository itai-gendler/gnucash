---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "export-report",
      "contexts": [
        {
          "place": "gnucash-desktop"
        },
        {
          "place": "gnucash-cli"
        }
      ]
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

# Report export diagnoses exporter and destination failures

Export/destination errors produce diagnostics; CLI output-file failure need not imply failed exit status.
