# evm-bytecode-practice
Repository dedicated to EVM bytecode programming.

## Installation
Make sure your global environment contains dapptools. To install dapptools on your local machine visit the dapptools [repo](https://github.com/dapphub/dapptools).

## Set Up Environment Variables
Create a `.env` file that will be used for the local dapp node. A sample .env file can be seen below:

```env
export ETH_KEYSTORE=~/.dapp/testnet/8545/keystore
export ETH_FROM=$(cat ~/.dapp/testnet/8545/config/account | head -n 1)
export ETH_FROM_2=$(cat ~/.dapp/testnet/8545/config/account | tail -n 1)
export ETH_PASSWORD=/dev/null
export ETH_GAS=1000000
export ETH_RPC_URL=http://localhost:8545
```

## Deploy a contract

1. Start up a local dapp testnet node

```bash
dapp testnet
```

2. Source environment variables

```bash
source .env
```

3. Deploy Bytecode

```bash
sed 's/\/\/.*//g' <file-path> | tr '\n' ' ' | sed 's/ //g' | xargs seth send --create
```
