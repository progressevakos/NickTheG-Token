# NickTheG Token

![GitHub repo size](https://img.shields.io/github/repo-size/progressevakos/NickTheG-Token)
![GitHub license](https://img.shields.io/github/license/progressevakos/NickTheG-Token)

## Introduction

The NickTheG Token is a token deployed on the RedBelly blockchain. It provides basic functionality for transferring tokens and managing token balances.

- **Name:** Redbelly Devnet
- **Symbol:** BU
- **Decimals:** 18
- **Total Supply:** 100,000,000

## Smart Contract Details

- **Smart Contract:** `NickTheG.sol`
- **Solidity Version:** 0.8.17

## Functions

### `constructor()`

- Initializes the contract with the owner's address and sets the initial total supply.

### `transfer(address recipient, uint256 amount)`

- Allows users to transfer tokens from their account to another account.

## Usage

### Deployment

1. Compile the smart contract using a Solidity compiler.
2. Deploy the compiled contract to an Ethereum network of your choice (mainnet, testnet, or a local development network).

### Interacting with the Contract

Example of transferring tokens using web3.js:

```javascript
const contractAddress = 0x3152070bf0394cc8b58d22bf5adaf069f4b8a875;
const contractABI = [...]; // Paste the ABI of your contract here
const web3 = new Web3('YOUR_WEB3_PROVIDER');

const contract = new web3.eth.Contract(contractABI, contractAddress);

// Transfer tokens
const recipient = 'RECIPIENT_ADDRESS';
const amount = 100; // Adjust the amount as needed

contract.methods.transfer(recipient, amount).send({ from: 'SENDER_ADDRESS' })
    .on('transactionHash', (hash) => {
        console.log('Transaction Hash:', hash);
    })
    .on('confirmation', (confirmationNumber, receipt) => {
        console.log('Confirmation Number:', confirmationNumber);
        console.log('Receipt:', receipt);
    })
    .on('error', (error) => {
        console.error('Error:', error.message);
    });
