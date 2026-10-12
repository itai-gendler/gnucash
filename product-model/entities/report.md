---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/report/report-core.scm"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-report.cpp"
    }
  ]
}
---

# Report

An opened working report instance, whose rendered content is a projection of accounting and options.

## Information kept

- **Name** — The working report’s displayed name.
- **Report type** — The selected report definition.
- **Options** — The selected account, date, currency and other report inputs.
- **Needs save** — Whether the working report is marked as requiring saved report state; desktop setup also marks a newly opened report.
- **Saved configuration** — The reusable configuration associated with the working report, when present.
- **Rendered content** — The rendered report output for its current inputs.
