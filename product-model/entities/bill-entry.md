---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/register/ledger-core/gncEntryLedgerModel.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncEntry.h"
    }
  ]
}
---

# Bill Entry

An independently selected ordinary bill ledger entry.

## Information kept

- **Date** — The entry date.
- **Description** — The entry description.
- **Action** — The retained entry action.
- **Quantity** — The entered quantity.
- **Price** — The unit price.
- **Expense account** — The expense account used for nonzero entry posting.
- **Billable** — Whether the bill entry is marked billable.
- **Taxable** — Whether the entry is taxable.
- **Tax included** — Whether its entered price includes tax.
- **Tax table** — The selected tax table.
- **Value** — The calculated entry value.
- **Tax value** — The calculated tax value.
