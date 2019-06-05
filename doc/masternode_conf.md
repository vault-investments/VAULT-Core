Multi masternode config
=======================

The multi masternode config allows you to control multiple masternodes from a single wallet. The wallet needs to have a valid collateral output of 1000 coins for each masternode. To use this, place a file named masternode.conf in the data directory of your install:
 * Windows: %APPDATA%\VAULT\
 * Mac OS: ~/Library/Application Support/VAULT/
 * Unix/Linux: ~/.vault/

The new masternode.conf format consists of a space seperated text file. Each line consisting of an alias, IP address followed by port, masternode private key, collateral output transaction id, collateral output index, donation address and donation percentage (the latter two are optional and should be in format "address:percentage").

Example:
```
mn1 127.0.0.2:14147 7oP8nRLzk7uHaLaSaR8GGiu8cZwXhyVAETzovJHidYEikUHiiWt e605b63dbadc354e93dd9590c3530e841c9a57d253fdb4a37ddf97b22cff572c 0
mn2 127.0.0.3:14147 7nbEhmD9UEgq8qTFTTGnLJG4pttmD4iXQwv9zB2xBs6SPY542Gq 4fbc1deef2cabd0bee91ae0dd25b7c85215475507819b96b69a60b019f51bdbd 0 VDEVXXjKFMrdimYyMd5HrsHfnACGknCS5Q:33
mn3 127.0.0.4:14147 7nMcwRAFg6Jez31RPfEKoD1WzobHfWVvJjyvScDQeoabb5pn5La b7a5a8d97d3669f6cd87ce5b132732f59c992a677d5fe3a40a4bca8c853cf753 1 VDEVXXjKFMrdimYyMd5HrsHfnACGknCS5Q
```

In the example above:
* the collateral for mn1 consists of transaction e605b63dbadc354e93dd9590c3530e841c9a57d253fdb4a37ddf97b22cff572c, output index 0 has amount 1000
* masternode 2 will donate 33% of its income
* masternode 3 will donate 100% of its income


The following new RPC commands are supported:
* list-conf: shows the parsed masternode.conf
* start-alias \<alias\>
* stop-alias \<alias\>
* start-many
* stop-many
* outputs: list available collateral output transaction ids and corresponding collateral output indexes

When using the multi masternode setup, it is advised to run the wallet with 'masternode=0' as it is not needed anymore.
