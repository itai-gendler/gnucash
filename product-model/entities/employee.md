---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-employee.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "libgnucash/engine/gncEmployee.c"
    }
  ],
  "relations": [
    {
      "entity": "expense-voucher",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ],
  "domain": "employee"
}
---

# Employee

An independently selected employee with contact and payment settings.

## Information kept

- **Number** — The employee number; a blank number is generated on save.
- **Username** — The employee’s retained username.
- **Payment contact** — Payment name, address, phone, fax and email details.
- **Active** — Whether the employee is active.
- **Language** — The language retained for the employee.
- **Workday** — The employee’s workday amount.
- **Rate** — The employee’s rate amount.
- **Currency** — The currency used for employee expense accounting.
- **Credit-card account** — The account selected for employee credit-card expenses.
- **Open balance** — The derived unsettled employee accounting balance.
