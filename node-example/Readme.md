# Run a MDC Validator
## Setting up a node
1. Git clone https://github.com/medoxsmartchain/MDCNetwork.git

2. Copy source form node-example to root folder
```
cp -r MDCNetwork/node-example/MDC  /root/
```
3. Create an Account

```
cd /root/MDC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
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

    To stake MDC coin, all you should do is sending your MDC coin to the MDC Consensus contract address over the MDC network from the validator address.
    The MDC Consensus contract address: 0x97547762d01e8b256eE5dfa3dDf6EEd30eB83e1B
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to MDC and send the MDC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /MDC/nodes/validator/keys/MDC/UTC--xxxx
    /MDC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
