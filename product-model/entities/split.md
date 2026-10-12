---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Split.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/xml/gnc-transaction-xml-v2.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/sql/gnc-transaction-sql.cpp"
    }
  ],
  "domain": "transaction"
}
---

# Split

An independently selected accounting split in a transaction, assigned to an account.

## Information kept

- **Account** — The account to which the amount is posted.
- **Memo** — The split’s memo.
- **Action** — The action or split-number value.
- **Amount** — The quantity in account commodity units.
- **Value** — The balancing value in transaction currency units.
- **Reconciliation status** — Unreconciled, cleared, reconciled, frozen or void status.
- **Reconciliation date** — The date retained by reconciliation or imported clearing.
- **Former amount** — The account quantity retained before voiding.
- **Former value** — The currency value retained before voiding.
- **Online identifier** — The imported online identity when supplied and retained by the format.
