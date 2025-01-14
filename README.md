# Temporal Public Testnet

To generate a gentx:

Clone and install the node:

```
git clone https://github.com/temporal-zone/temporal.git
cd temporal
git checkout v0.2.1
make install
```

Restore your keys:

```
temporald keys add NAME_OF_KEY
temporald keys list
```

Copy your new temporal address

Init the node, add a genesis account and generate the gentx:

```
temporald init NODE_NAME --chain-id temporal-test-1 --default-denom utprl
temporald add-genesis-account TEMPORAL_ADDRESS 1000000000000utprl
```
Note: if you get an error that it `failed to to get address from Keybase`, try adding `--keyring-backend os`, unless when you restored your keys you explicitly specificed a different `keyring-backend`, then use that one.

```
temporald gentx NAME_OF_KEY 1000000000000utprl \
--chain-id temporal-test-1 \
--moniker="YOUR_VALIDATOR_NAME" \
--commission-rate 0.05 \
--commission-max-rate 0.10 \
--commission-max-change-rate 0.05 \
--details="XXXXXXXX" \
--identity YOUR_KEYBASE_ID \
--security-contact="XXXXXXXX" \
--website="XXXXXXXX"
```

Please then submit the gentx-UNIQUE_ID.json file to the gentx folder in this repo.
