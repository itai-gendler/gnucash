---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-sx-editor.c#gnc_sxed_save_sx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/app-utils/gnc-sx-instance-model.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/xml/gnc-schedxaction-xml-v2.cpp"
    }
  ],
  "relations": [
    {
      "entity": "transaction",
      "verb": "produces",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "scheduled-transactions"
}
---

# Scheduled Transaction

A named recurrence definition and accounting template with retained occurrence progress.

## Information kept

- **Name** — The definition’s displayed name; duplicate names can be accepted after warning.
- **Enabled** — Whether occurrence processing includes this definition.
- **Recurrence** — The repeat interval and calendar schedule.
- **Start** — The beginning date for occurrences.
- **End condition** — The selected end date, occurrence limit or no-end condition.
- **Automatic creation** — Whether eligible occurrences are created without manual acceptance.
- **Notify** — Whether automatic creation is reported to the user.
- **Creation lead days** — How far ahead occurrences become eligible for creation.
- **Reminder lead days** — How far ahead occurrences are presented as reminders.
- **Template content** — The accounts, formulas and accounting template used to generate transactions.
- **Last occurrence** — The date retained as occurrence progress advances.
- **Remaining occurrences** — The count remaining under an occurrence-limited end condition.
- **Deferred occurrences** — The occurrences retained for postponed processing.
- **Instance count** — The retained occurrence counter used during generation.
