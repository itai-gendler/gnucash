---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "main": "GnuCash continuation"
  },
  "steps": [
    {
      "text": "Application Preferences enables hierarchy setup on a new Book.",
      "kind": "condition",
      "entities": [
        {
          "entity": "book",
          "effect": "reads",
          "facts": []
        },
        {
          "entity": "application-preferences",
          "effect": "reads",
          "facts": []
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      }
    },
    {
      "text": "Choose New and resolve current unsaved changes.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "new-book"
    },
    {
      "text": "The Product creates an empty current Book with a writable session and no source location. The Product opens hierarchy setup.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "creates",
          "facts": [
            "Location",
            "Session access",
            "Unsaved changes",
            "Saved contents",
            "Transaction read-only period",
            "Transaction read-only cutoff",
            "Trading accounts",
            "Number source",
            "Default invoice report"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "new-book"
    },
    {
      "text": "Choose a template hierarchy, commodity and nonzero opening balances, then finish.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::account-hierarchy"
        }
      },
      "actor": "user",
      "capability": "create-account"
    },
    {
      "text": "The Product creates or merges selected Accounts and any nonzero opening-balance Transactions with dependent Splits; the Book becomes unsaved. The Product invokes Save As after hierarchy completion.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "creates",
          "facts": [
            "Name",
            "Code",
            "Description",
            "Notes",
            "Type",
            "Commodity",
            "Precision",
            "Parent",
            "Placeholder",
            "Hidden",
            "Opening balance account",
            "Tax related",
            "Lower balance limit",
            "Upper balance limit",
            "Include subaccounts in balance limits",
            "Balance",
            "Cleared balance",
            "Reconciled balance",
            "Last reconciliation date",
            "Reconciliation interval",
            "Include subaccounts",
            "Postponed statement date",
            "Postponed ending balance"
          ]
        },
        {
          "entity": "transaction",
          "effect": "creates",
          "facts": [
            "Posted date",
            "Entered date",
            "Number",
            "Description",
            "Notes",
            "Currency",
            "Read-only reason",
            "Void reason",
            "Void time",
            "Former notes",
            "Reversing transaction",
            "Scheduled source",
            "Document link"
          ],
          "to": "Active"
        },
        {
          "entity": "split",
          "effect": "creates",
          "facts": [
            "Account",
            "Memo",
            "Action",
            "Amount",
            "Value",
            "Reconciliation status",
            "Reconciliation date",
            "Former amount",
            "Former value",
            "Online identifier"
          ],
          "with": "transaction"
        },
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Unsaved changes"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop::account-hierarchy"
        }
      },
      "actor": "user",
      "capability": "create-account"
    },
    {
      "text": "Choose Save As and a valid new destination.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "save-book-as"
    },
    {
      "text": "The Product establishes the selected destination as the Book’s writable source.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Location",
            "Session access"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "save-book-as"
    },
    {
      "text": "The Product persists the Book’s current accounting at that writable destination and clears unsaved changes.",
      "kind": "product",
      "entities": [
        {
          "entity": "book",
          "effect": "changes",
          "facts": [
            "Saved contents",
            "Unsaved changes"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "gnucash-desktop"
        }
      },
      "actor": "user",
      "capability": "save-book-as"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/gnc-file.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-account-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome-utils/dialog-account.c#gnc_ui_to_account"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/assistant-hierarchy.cpp#on_finish"
    }
  ]
}
---

# Hierarchy preference enabled

## Trigger

New-book creation runs with Show hierarchy on new book enabled; the user finishes the supplied hierarchy and destination continuation.

## Outcome

The new Book, selected Account hierarchy and opening accounting are persisted.
