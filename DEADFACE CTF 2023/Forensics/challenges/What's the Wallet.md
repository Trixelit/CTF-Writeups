# What's the Wallet (20)

## Challenge Description
Ransomware was recently discovered on a system within De Monne’s network courtesy of a DEADFACE member. Luckily, they were able to restore from backups. You have been tasked with finding the Bitcoin wallet address from the provided sample so that it can be reported to the authorities. Locate the wallet address in the code sample and submit the flag as ```flag{wallet_address}```.

## Solution

By quickly skimming over the provided file ['Bitcoin.txt'](../files/whats_the_wallet/Bitcoin.txt) we can see that there is a string encoded in base64 on line 48 labelled 'BtcWalletAddress'.

By running the command ```echo "bjMzaGE1bm96aXhlNnJyZzcxa2d3eWlubWt1c3gy" | base64 -d``` in a terminal, we get the decoded address.

Our flag is ```flag{n33ha5nozixe6rrg71kgwyinmkusx2}```.