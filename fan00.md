# fan 00

## Ledger entry

This note aims to describe the structure for a debit / credit ledger entry.  
There is just one transfer per event possible. Multi-debit-muli-credit-transfers should be handled, if not divisible in single events, over control-accounts / clearing-accounts. 

## Format of ledger entry event

~~~yaml
{
  "id": <32-bytes lowercase hex-encoded sha256 of the serialized posting data>,
  "pubkey": <32-bytes lowercase hex-encoded public key of the posting creator>,
  "created_at": <unix timestamp in seconds>, //this should be used as timestamp of the posting period to which the posting should belong, rather than the real creation timestamp for better filtering
  "kind": 8711, //
  "tags": [
debit_lacc
credit_lacc
amount
unit
scale
creation date
accounting area
ledger structure reference
posting partner
movement type / sl reference / external reference / media reference
  ]
  "content": <optional posting description/comment>
  "sig": <64-bytes lowercase hex of the signature of the sha256 hash of the serialized event data, which is the same as the "id" field>
}
~~~

The structure ensures that debit and credits equal, if valid 'debit_lacc' and 'credit_lacc' are specified.  
The movement-flow of the transfer can be normally interpreted as going from the 'credit_lacc' to the 'debit_lacc' account.  
  
This note should introduce the "je_movement_type" (0, "general ledger movement"), "kind" (8001, "general ledger entry").
