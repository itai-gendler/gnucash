---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/assistant-hierarchy.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/reconcile-view.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/window-reconcile.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/import-export/import-main-matcher.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-sx-since-last-run.c"
    }
  ],
  "singleton": true
}
---

# Application Preferences

The current application profile’s inspected preferences, whose consumption affects accounting hand-offs and matching.

## Information kept

- **Show hierarchy on new book** — Whether creation opens account-hierarchy setup.
- **Check cleared splits** — Whether eligible cleared splits are initially selected for reconciliation.
- **Prompt for credit-card payment** — Whether eligible completed credit-card reconciliation offers a payment transfer.
- **Import updates enabled** — Whether matching offers replacement of transaction details.
- **Run schedules on book open** — Whether book opening invokes schedule processing.
