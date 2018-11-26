# Design-Docs

This repository is for documents to describe various features of ONOchain.

ONOchain is based on the EOSIO (https://github.com/EOSIO/eos) and adapted for use in the ONO environment.

The intention is to minimize the changes to EOSIO, to be able to most easily track and follow changes made to EOSIO, while maintaining the unique features of ONO.

ONOchain uses ONOT as its base token. At start, ONOT are created based on frozen ERC20 ONOT contracts, and are also imported from the interim ONO user database from the ONO servers.

ONOchain user IDs are mapped from the ONO user database, which uses numeric IDS, into the EOS style 12 character account names. EOS account names are the representation using the character set [a-z1-5] of a 64-bit integer. Special named accounts of the form \*.ono are made for system specific use.

ONOchain does not charge end users for RAM for basic account data. The cost of such RAM is borne by the system. Add on dapps, built to run on the ONOchain, may have RAM costs associated with their operation. 

Most user activity, such as like, unlike, re-ono, token transfers, and account setting changes, are recorded into the ONOchain. Uploaded content of all type, text, pictures and video, are stored in a distributed storage service installed at multiple sites globally, for redundacy and performance. 

The ONOapi servers allow for public query of the blockchain and the storage service via the same api or rpc query. These servers are distributed globally, and supported by each block producer. The storage servers are not directly accessible to public query.

Specific implementation of these features will be released in this repository as they are developed and fit for review. We will not put all work in progress here, but instead will make period public release of the components as it makes sense to the developers.
