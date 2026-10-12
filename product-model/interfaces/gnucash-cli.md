---
{
  "type": "cli",
  "actors": [
    "user"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-cli.cpp#GnucashCli::start"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "gnucash/gnucash-commands.cpp"
    }
  ]
}
---

# GnuCash CLI

The command-line contract lists, describes, renders and exports reports; reports read books without posting. It also describes quote sources, fetches quotes into a book and dumps requested quote results. Backend connection credentials do not establish a GnuCash role.
