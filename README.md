# Note

This implementation proposals aim to be a on nostr events based form for exchanging (financial) accounting data.  
(The target is financial accounting, but the data structure is more general and could be also used for other forms of accounting).
  
It is implementations of nostr events from nostr-protocol. So in doubt and for everything not covered here (e.g. data flow) one should refer to the nostr-protocol specification.  

# The following new kinds, tags and for this implementation specific "je_movement_types" are introduced

## Implementation proposals:
0 - General Ledger Entry
1 - Accounting area
2 - Accounts structure

## Event kinds:
- from 0 -
(8001, general ledger entry)
- from 1 -
(38001, accounting area event)
- from 2 -
(38002, accounts structure event)

## Tags:
- from 0 -
(accounting_area, ")
(je_movement_types, ")
(subledger_reference, ")
(je_posting_partner, ")
(je_creation_date, ")
(journal_entry, ")
(je_backup, ")
- from 1 -
(accounts_structure, ")
(poster_rules, ")
- from 2 -
(account, ")

## "Je_movement_types":
- from 0 -
(0, general ledger movement)
