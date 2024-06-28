# DivyaToken-Eth-Avax-Module-3

DivyaToken is a simple ERC-20 token smart contract written in Solidity. It provides basic functionality for managing a custom token called "DivyaToken" (DT).

## Overview

This smart contract implements the following features:

### Contract Details

- **Name**: DivyaToken
- **Symbol**: Customizable upon deployment
- **Owner**: The deployer of the contract
- **Total Supply**: Tracks the total supply of the token
- **Balances**: Tracks the balance of each address

## Functions

- **mint**: Allows the contract owner to mint new DT tokens and distribute them to an address.
- **burn**: Allows a token holder to burn (destroy) their own DT tokens.
- **transfer**: Allows token holders to transfer DT tokens to another address.

## Usage

1. Deploy the smart contract to the Ethereum network.
2. Interact with the contract using the provided functions.
   - Use the `mint` function to create new DT tokens.
   - Use the `burn` function to destroy DT tokens.
   - Use the `transfer` function to send DT tokens to another address.

## Deployment

To deploy the DivyaToken contract:

1. Use a Solidity development environment like Remix or Truffle.
2. Set the Solidity version to ^0.8.0.
3. Deploy the contract to an Ethereum network of your choice.
4. After deployment, the contract owner can use the `mint` function to create and distribute new SDT tokens.

## Security Considerations

This is a simple example contract and does not implement advanced security features. It's recommended to review and audit the contract code thoroughly before deploying it to a production environment.

## License

This smart contract is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
