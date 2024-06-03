# Run a ERAM Validator
## Setting up a node
1. Git clone https://github.com/eramsmartchain/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/ERAM  /root/
```
3. Create an Account

```
cd /root/ERAM
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake ERAM coin, all you should do is sending your ERAM coin to the ERAM Consensus contract address over the ERAM network from the validator address.
    The ERAM Consensus contract address: 0x476c29c5589BFE3C0E4A509bb92545882bb4Db82
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to ERAM and send the ERAM coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /ERAM/nodes/validator/keys/ERAM/UTC--xxxx
    /ERAM/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
