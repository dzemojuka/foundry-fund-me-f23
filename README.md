# Foundry Fund Me

This project is a part of the [Cyfrin](https://github.com/Cyfrin) Solidity Course.

# Getting Started

## Requirements

[git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
[foundry](https://getfoundry.sh/)

## Quickstart

```bash
git clone https://github.com/Cyfrin/foundry-fund-me-f23
cd foundry-fund-me-f23
forge build
```

# Usage

Deploy:

```bash
forge script scripts/DeployFundMe.s.sol
```

## Testing

```bash
forge test
```

or

```bash
// Only run test functions matching the specified regex pattern.

forge test --match-test testFunctionName
```

or

```bash
 forge test --fork-url $SEPOLIA_RPC_URL
```

## Test coverage

```bash
forge coverage
```

# Deploy to a testnet or mainnet

1. Setup environment variables

You'll want to set your **SEPOLIA_RPC_URL** and **PRIVATE_KEY** as environment variables. You can add them to a **.env file**, similar to what you see in **.env.example**.

- PRIVATE*KEY: The private key of your account (like from [metamask](https://metamask.io/)). \*\*\_NOTE:*\*\* FOR DEVELOPMENT, PLEASE USE A KEY THAT DOESN'T HAVE ANY REAL FUNDS ASSOCIATED WITH IT.
  - You can [learn how to export it here](https://support.metamask.io/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key).
- SEPOLIA_RPC_URL: This is url of the goerli testnet node you're working with. You can get setup with one for free from [Alchemy](https://www.alchemy.com/?a=673c802981)

Optionally, add your **ETHERSCAN_API_KEY** if you want to verify your contract on [Etherscan](https://etherscan.io/).

2. Get testnet ETH

Head over to [faucets.chain.link](https://faucets.chain.link/) and get some tesnet ETH. You should see the ETH show up in your metamask.

3. Deploy

```bash
forge script script/DeployFundMe.s.sol --rpc-url $SEPOLIA_RPC_URL --private-key $PRIVATE_KEY --broadcast --verify --etherscan-api-key $ETHERSCAN_API_KEY
```

## Scripts

After deploy to a testnet or local net, you can run the scripts.

Using cast deployed locally example:

```bash
cast send <FUNDME_CONTRACT_ADDRESS> "fund()" --value 0.1ether --private-key <PRIVATE_KEY>
```

or

```bash
forge script script/FundFundMe.s.sol --rpc-url sepolia  --private-key $PRIVATE_KEY  --broadcast
```

## Withdraw

```bash
cast send <FUNDME_CONTRACT_ADDRESS> "withdraw()"  --private-key <PRIVATE_KEY>
```

## Estimate gas

You can estimate how much gas things cost by running:

```bash
forge snapshot
```

And you'll see and output file called **.gas-snapshot**.

# Formatting

To run code formatting:

```bash
forge fmt
```

# THANK YOU!
