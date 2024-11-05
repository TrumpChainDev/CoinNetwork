# Run a DJT Validator
## Setting up a node
1. Git clone https://github.com/TrumpChainDev/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/DJT  /root/
```
3. Create an Account

```
cd /root/DJT
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

    To stake DJT coin, all you should do is sending your DJT coin to the DJT Consensus contract address over the DJT network from the validator address.
    The DJT Consensus contract address: 0x3FA18721a6D5eAd62d77f1E9DA4D848d4fb4461A
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to DJT and send the DJT coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /DJT/nodes/validator/keys/DJT/UTC--xxxx
    /DJT/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
