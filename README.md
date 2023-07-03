# Ethereum Multi-sig Wallet

See it live [here](https://ethereum-multi-sig-wallet.vercel.app/)

## Prerequisites

1. Follow [this guide](https://devtonight.com/posts/metamask-testnet-wallet-setup-for-blockchain-development) to create an Ethereum wallet and switch to the Rinkeby Test Network
2. Send yourself some test ETH [here](https://faucets.chain.link/rinkeby)

## Overview

This is an open-source implementation of an Ethereum multi-sig wallet with a React-based UI. A multi-sig wallet is a cryptocurrency wallet that requires two or more private keys to sign and send a transaction. The purpose of this project is to encourage new Solidity developers to get started with open-source development.

## Getting started

1. Clone the repository: `git clone https://github.com/florolf1/florolf-multi-sig-wallet.git`
2. Install dependencies: `npm install`
3. Compile the contracts: `npx hardhat compile`

## Deploy locally

### Prerequisites

- Browser-based Ethereum wallet [(ex: MetaMask)](https://metamask.io/)
- PostgreSQL database on Heroku [(see this guide)](https://dev.to/prisma/how-to-setup-a-free-postgresql-database-on-heroku-1dc1)

### Deployment

1. Update `DATABASE_URL` in the `.env` file
2. Open a terminal window and run `npx prisma db push`
3. Run `npx hardhat node`
4. Create a new wallet by importing the secret key from one of the Hardhat accounts
5. Open a second terminal window and run `npx hardhat run scripts/deploy.js --network localhost`
6. Change networks in Metamask to Localhost8545
7. Copy the address of the deployed factory contract and update the value stored in `config.js`
8. Open a third terminal window and run `npm run dev`

## Testing

- Run `npx hardhat test`

## Etherscan verification

```shell
hardhat run --network ropsten scripts/deploy.js
```

Then, copy the deployment address and paste it in to replace `DEPLOYED_CONTRACT_ADDRESS` in this command:

```shell
npx hardhat verify --network ropsten DEPLOYED_CONTRACT_ADDRESS "Hello, Hardhat!"
```

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Technologies

- [Solidity](https://docs.soliditylang.org/en/v0.8.11/)
- [Hardhat](https://hardhat.org/)
- [Ethers.js](https://docs.ethers.io/v5/)
- [Waffle](https://ethereum-waffle.readthedocs.io/en/latest/)
- [Next.js](https://nextjs.org/)
- [Prisma](https://www.prisma.io/docs/)
- [Redux Toolkit](https://redux-toolkit.js.org/usage/usage-guide)
- [MaterialUI](https://mui.com/getting-started/installation/)
