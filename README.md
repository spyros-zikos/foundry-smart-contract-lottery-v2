## Raffle Smart Contract
Deployed at `0x355b7F6CA973871219B66645a4e9B7C520314883`

## Usage

### 1. Create account from private key (If you don't already have one)
(Account needs to have at least 100 Testnet LINK and some Sepolia ETH)
```bash
cast wallet import myaccount -i
```
Note: You can choose any account name instead of "myaccount".
### 2. Make a .env file in root directory
```
SEPOLIA_RPC_URL=https://eth-sepolia.g.alchemy.com/v2/...
ETHERSCAN_API_KEY=...
ACCOUNT_NAME=... (The name of the account that you created in the previous step.)
ACCOUNT_ADDRESS=0x... (The address of the account that you created.)
SEPOLIA_SUB_ID=0 (If you have a VRF subscription id, put it here. Otherwise you will generate one below.)
```
### 3. Build the project
```bash
make build
```
### 4. Get VRF subscription id
```bash
make deploy-sepolia
```
Go to https://vrf.chain.link/sepolia and get the subscription id from `My Subscriptions` section. (You may have to wait a while until it shows up.)  
Then replace `0` with the new id in the `SEPOLIA_SUB_ID` variable of the `.env` file.
### 5. Deploy Raffle to Sepolia
```bash
make deploy-sepolia
```
### 6. After deploying
- Go to `https://automation.chain.link/sepolia/new` and register a new custom upkeep.  
- If you don't want to register a custom upkeep you can call the `performUpkeep` function manually.