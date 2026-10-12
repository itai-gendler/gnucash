---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-account.c#gnc_ui_to_account"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/Account.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/window-reconcile.cpp"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "split",
      "verb": "contains",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Account

An independently selected account in the book’s hierarchy, with commodity, balance and reconciliation information.

## Information kept

- **Name** — The account’s displayed name.
- **Code** — The optional account code.
- **Description** — The account description.
- **Notes** — Notes retained for this account.
- **Type** — The accounting account type.
- **Commodity** — The currency or security in which the account’s amounts are expressed.
- **Precision** — The account’s smallest permitted commodity fraction.
- **Parent** — The account’s position under its selected parent.
- **Placeholder** — Whether the account is a placeholder rather than an ordinary posting account.
- **Hidden** — Whether the account is hidden from ordinary account selection.
- **Opening balance account** — Whether this account is designated for opening-balance accounting.
- **Tax related** — Whether the account is marked tax related.
- **Lower balance limit** — The configured lower account-balance warning limit.
- **Upper balance limit** — The configured upper account-balance warning limit.
- **Include subaccounts in balance limits** — Whether limit checking includes subaccount balances.
- **Balance** — The derived sum of account split amounts.
- **Cleared balance** — The derived balance of splits whose reconciliation status is not unreconciled.
- **Reconciled balance** — The derived balance of reconciled or frozen splits.
- **Last reconciliation date** — The statement date retained on completed reconciliation.
- **Reconciliation interval** — The interval used to suggest future reconciliation dates.
- **Include subaccounts** — The retained reconciliation choice to include compatible subaccounts.
- **Postponed statement date** — The statement date retained when reconciliation is postponed.
- **Postponed ending balance** — The statement ending balance retained when reconciliation is postponed.
