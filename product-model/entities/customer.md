---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-customer.c#gnc_ui_to_customer"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncCustomer.c"
    }
  ],
  "relations": [
    {
      "entity": "invoice",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "job",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "customer"
}
---

# Customer

A customer addressed independently through business forms and searches.

## Information kept

- **Number** — The customer number; a blank number is generated on save.
- **Name** — The customer’s company name.
- **Billing contact** — Billing name, address, phone, fax and email details.
- **Shipping contact** — Shipping name, address, phone, fax and email details.
- **Active** — Whether the customer is active.
- **Currency** — The currency used for the customer’s business accounting.
- **Terms** — The selected billing terms.
- **Tax settings** — The tax inclusion and tax-table settings.
- **Discount** — The customer discount percentage.
- **Credit limit** — The retained customer credit limit; retention does not promise invoice enforcement.
- **Notes** — Notes about the customer.
- **Open balance** — The derived unsettled customer accounting balance.
