---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-employee",
      "contexts": [
        {
          "place": "gnucash-desktop::employees"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/dialog-employee.c"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-page-owner-tree.cpp"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnome/gnc-plugin-business.c"
    }
  ]
}
---

# Employee overview editing has a read-only action gate

The Employee overview enables its edit action only with a selected record in a writable Book. This entry-route check does not establish a universal restriction on independently reached editing dialogs.
