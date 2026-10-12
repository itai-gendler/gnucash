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

# Invoice Entry

An independently selected ordinary invoice ledger entry.

## Information kept

- **Date** — The entry date.
- **Description** — The entry description.
- **Action** — The retained entry action.
- **Quantity** — The entered quantity.
- **Price** — The unit price.
- **Income account** — The income account used for nonzero entry posting.
- **Discount** — The entry discount.
- **Discount type** — Whether discount is a value or percentage.
- **Discount application** — How discount applies in the value/tax calculation.
- **Taxable** — Whether the entry is taxable.
- **Tax included** — Whether its entered price includes tax.
- **Tax table** — The selected tax table.
- **Value** — The calculated entry value.
- **Tax value** — The calculated tax value.
