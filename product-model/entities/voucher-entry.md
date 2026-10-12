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

# Voucher Entry

An independently selected ordinary employee voucher ledger entry.

## Information kept

- **Date** — The entry date.
- **Description** — The entry description.
- **Action** — The retained entry action.
- **Quantity** — The entered quantity.
- **Price** — The unit price.
- **Expense account** — The expense account used for nonzero entry posting.
- **Billable** — Whether the voucher entry is marked billable.
- **Payment type** — Cash or credit-card expense payment type.
- **Value** — The calculated entry value.
