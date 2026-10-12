---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/report-core.scm#gnc:report-to-template"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/gnc-report.cpp#gnc_saved_reports_write_to_file"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-custom-report.c"
    }
  ],
  "relations": [
    {
      "entity": "report",
      "verb": "instantiates",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Saved Report Configuration

An independently reusable named configuration kept in the user’s saved-report data, separately from book accounting.

## Information kept

- **Name** — The independently retained configuration name.
- **Report type** — The report definition from which the configuration derives.
- **Options** — The saved report options.
- **Embedded configurations** — The saved child-report configurations for supported composite reports.
