# Release version

We are waiting for EOSIO release 1.6.0, which has some important updates related to both performance and security. 
Testing on testnets with 1.6.0-rc2 are going well. This version will be the bassis to launch ONOchain.

# Minimal modifications

Our philosophy is to minimize the changes we make to the base code, so that future improvements can be easily incorporated. 
To accomplish this, we try to implement our special functions via system accounts with special priviledges, 
small system contract changes, and a slow, deliberate pace to be certain that everything is working correctly.

While some may look for big, significant changes, we think this is not a correct approach, 
choosing instead to test and design small changes to the base code.

# Account mapping

EOSIO uses account names, to which multiple keys are associated, with designated permission levels.
Account names in EOSIO are internally represented as 64-bit integers, and displayed as 12 character names 
using the character set [a-z1-5]. 
Since ONO accounts in the existing ONO app and web server system are represented as a unique number, 
we shall map the number into a 64 bit integer, and use that as the account name.

At activation of the chain, accounts will be created as they are used. Instead of stopping the app 
and servers to create and synchronize all chain accounts, we will migrate and synchronize over time. 
Any transaction where the account is used will cause the account to be created, and its ONOT to be populated.

# Special accounts

The admin.ono account will start with a total number of ONOT equivalent to the ONOT allocated to app users. 
These ONOT will be sent to the user accounts as those accounts are created.

# ERC-20 migration

ONOT held via ERC-20 on the Ethereum blockchain, and currently tradeable on some exchanges, will not be migrated immediately. 
These will be frozen on Ethereum and migrated to ONOchain after clear coordination with exchanges and ERC-20 holders.
