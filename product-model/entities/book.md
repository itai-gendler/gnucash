---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/gnc-file.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/qofbook.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/xml/gnc-backend-xml.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/sql/gnc-sql-backend.cpp"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "transaction",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "scheduled-transaction",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "budget",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "customer",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "vendor",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "employee",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "job",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "invoice",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "bill",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "expense-voucher",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "payment",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "security",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "price",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Book

The accounting book selected in a session, together with its source and accounting options.

## Information kept

- **Location** — The file or database source associated with the current book.
- **Session access** — Writable or Read-only access established when opening or selecting the destination.
- **Unsaved changes** — Whether current accounting differs from its persisted contents.
- **Saved contents** — The last persisted accounting contents of the book.
- **Transaction read-only period** — The configured age-based restriction on ordinary transaction editing; zero disables that restriction.
- **Transaction read-only cutoff** — The derived earliest eligible posted date when the read-only period is active.
- **Trading accounts** — Whether trading-account accounting is used for commodity imbalance handling.
- **Number source** — Whether transaction number or split action supplies the register number.
- **Default invoice report** — The configured report used for invoice presentation.
