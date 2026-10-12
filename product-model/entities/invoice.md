---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-invoice.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncInvoice.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/backend/sql/gnc-invoice-sql.cpp"
    }
  ],
  "relations": [
    {
      "entity": "invoice-entry",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "transaction",
      "verb": "posts",
      "cardinality": "one-to-one"
    }
  ]
}
---

# Invoice

A separately selected invoice, including its corresponding credit-note cases, with ordinary entries and posting/settlement information.

## Information kept

- **Number** — The business-document number, generated when blank on accepted creation.
- **Billing reference** — The retained billing reference.
- **Owner** — The customer, vendor or employee, optionally through an associated job where supported.
- **Opening date** — The document’s opening date.
- **Currency** — The end owner’s accounting currency.
- **Terms** — The document’s selected billing terms.
- **Active** — Whether the document is active; posted metadata callbacks can retain this fact.
- **Notes** — Document notes; posted metadata callbacks can retain this fact.
- **Document type** — Ordinary document or the corresponding credit-note case.
- **Posted** — Whether the document currently has posting accounting.
- **Posting date** — The date used for posted accounting.
- **Due date** — The due date retained with posting.
- **Posting account** — The selected receivable or payable account.
- **Posting transaction** — The associated protected accounting transaction.
- **Totals** — Calculated entry and tax totals.
- **Outstanding amount** — The derived unsettled document amount.
- **Paid** — Whether the posted document’s lot is closed.

## States

### Unposted

The document has no current posting transaction and its ordinary entries can be prepared.

### Posted

The document retains its posting accounting and posting associations.
