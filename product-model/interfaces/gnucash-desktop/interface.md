---
{
  "type": "desktop-app",
  "actors": [
    "user"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash.cpp#scm_run_gnucash"
    }
  ]
}
---

# GnuCash

The desktop contract provides the selected accounting workflows in the current book, including read-only sessions. Opening a book does not require a GnuCash identity sign-in.
