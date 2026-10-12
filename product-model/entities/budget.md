---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gnc-budget.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-budget-view.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/xml/gnc-budget-xml-v2.cpp"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "budgets",
      "cardinality": "many-to-many"
    }
  ],
  "domain": "budget"
}
---

# Budget

A separately opened budget with period-based account values and notes.

## Information kept

- **Name** — The budget’s displayed name.
- **Description** — The description retained with the budget.
- **Recurrence** — The recurrence that defines budget periods.
- **Period count** — The number of periods.
- **Account-period amounts** — The explicitly set amounts for accounts and periods; an unset amount remains distinct from zero.
- **Account-period notes** — Notes retained for an account and budget period.
