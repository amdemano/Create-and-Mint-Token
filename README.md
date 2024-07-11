# MyToken ERC20 Smart Contract

This repository contains the implementation of an ERC20 token named `MyToken` (symbol: `MTK`). The smart contract is written in Solidity and designed to be deployed on the Ethereum blockchain. 
The contract uses OpenZeppelin libraries to ensure security and standard functionality.

## Features

- **Minting**: The contract owner can mint new tokens.
- **Burning**: Any token holder can burn their own tokens.
- **Transfer**: Standard ERC20 token transfer functionality.

## Requirements

- Solidity `^0.8.0`
- OpenZeppelin Contracts

## Installation

To use this contract, ensure you have the following installed:

- Node.js
- npm (Node Package Manager)
- Truffle or Hardhat (for contract deployment and testing)

Install the required dependencies:

```bash
npm install @openzeppelin/contracts
