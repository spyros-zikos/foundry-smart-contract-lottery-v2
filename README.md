## Raffle Smart Contract
Deployed at `0x355b7F6CA973871219B66645a4e9B7C520314883`

## Usage

### Store private key in account
(Need to have at least 100 Testnet LINK)
```bash
cast wallet import myaccount -i
```
### Make a .env file in root directory
```
SEPOLIA_RPC_URL=https://eth-sepolia.g.alchemy.com/v2/...
ETHERSCAN_API_KEY=...
```
### Deploy Raffle to Sepolia
```bash
source .env
make deploy-sepolia
```
After deploying:  
- Go to `https://automation.chain.link/sepolia/new` and register a new custom upkeep.  
- Check the console logs, get the subscriptionId and change line 61 of the `script/HelperConfig.s.sol` file accordingly, so that you won't create a new subscription if you redeploy.