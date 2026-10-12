---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-payment.c#gnc_payment_ok_cb"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncOwner.c#gncOwnerApplyPaymentSecs"
    }
  ],
  "relations": [
    {
      "entity": "transaction",
      "verb": "records",
      "cardinality": "one-to-one"
    },
    {
      "entity": "invoice",
      "verb": "settles",
      "cardinality": "many-to-many"
    },
    {
      "entity": "bill",
      "verb": "settles",
      "cardinality": "many-to-many"
    },
    {
      "entity": "expense-voucher",
      "verb": "settles",
      "cardinality": "many-to-many"
    }
  ]
}
---

# Payment

An independently selected business payment with accounting movement and document allocation information.

## Information kept

- **Company** — The customer, vendor or employee whose accounting receives the payment.
- **Date** — The payment’s accounting date.
- **Number** — The payment number.
- **Memo** — The payment memo.
- **Amount** — The nonzero money amount represented by the movement.
- **Posting account** — The receivable or payable account used for owner settlement.
- **Transfer account** — The account carrying the money movement.
- **Document allocations** — The selected documents and retained or derived settlement allocations.
- **Unapplied amount** — The amount left without a matching document allocation.
- **Accounting transaction** — The transaction recording the money movement.
