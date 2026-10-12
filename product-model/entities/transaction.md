---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Transaction.cpp"
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
  "relations": [
    {
      "entity": "split",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "transaction",
      "verb": "has reversal",
      "cardinality": "one-to-one"
    }
  ],
  "domain": "transaction"
}
---

# Transaction

A dated accounting transaction whose currency values are distributed among splits.

## Information kept

- **Posted date** — The accounting date used for posting and age-based editing checks.
- **Entered date** — The recorded entry timestamp.
- **Number** — The transaction number, interpreted with the book’s number-source setting.
- **Description** — The transaction’s displayed description.
- **Notes** — Notes retained on the transaction.
- **Currency** — The currency in which split values balance.
- **Read-only reason** — An explicit protection reason, including business-posted or voided accounting.
- **Void reason** — The supplied explanation for voiding.
- **Void time** — The timestamp recorded when voided.
- **Former notes** — The notes saved before voiding.
- **Reversing transaction** — The association with an existing linked inverse transaction.
- **Scheduled source** — The scheduled definition that generated the transaction, when applicable.
- **Document link** — The business-document or linked-document association, when present.

## States

### Active

Accounting values are retained in the ordinary active transaction.

### Voided

Former values and notes are retained while current split values are zero and the void reason/time is kept.
