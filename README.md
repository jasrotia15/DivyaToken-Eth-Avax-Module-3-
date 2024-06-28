# DivyaToken-Eth-Avax-Module-3
## Description

This repository contains the Solidity code for the DivyaToken smart contract. DivyaToken is a simple ERC-20 token smart contract written in Solidity. It provides basic functionality for managing a custom token called "DivyaToken".

### Contract Details

- **Name**: DivyaToken
- **Symbol**: Customizable upon deployment
- **Owner**: The deployer of the contract
- **Total Supply**: Tracks the total supply of the token
- **Balances**: Tracks the balance of each address

## Getting Started
For this project, I am asked to write a smart contract to create my own ERC20 token and deploy it using HardHat or Remix and also from te chosen tool , the contract owner should be able to mint tokens to a provided address and any user should be able to burn and transfer tokens.
```javascript
pragma solidity ^0.8.18;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract DivyaToken is ERC20 {
    address public owner;
    uint public TotalSupply;

```
The import "@openzeppelin/contracts/token/ERC20/ERC20.sol"; line is used to import the ERC20 contract from the OpenZeppelin library. It  provides all the features that is needed to create an ERC20 token, such as the ability to transfer tokens, mint new tokens,etc. The contract HarshDeoRavi is ERC20 line declares a new contract called HarshDeoRavi that inherits from the ERC20 contract meaning that it will have all features of ERC20. The public variables owner and TotalSupply is declared.  
   
Next, 
```javascript
constructor(string memory TokenName, string memory TokenSymbol) ERC20(TokenName, TokenSymbol) {
        owner = msg.sender;
```
The above given code initializes the contract with token name and token symbol and sets the owner as the deployer
```javascript
    modifier onlyOwner() {
        require(msg.sender == owner, "Only the contract owner can call this function");
```
The modifier function given above ensures that only the owner of the contract is using it. 

```javascript
 function CheckBalance () view public returns (uint){
        return balance;
```
The CheckBalance() function is a function that returns the total balance of the contract. In other words, it allows anyone to view the total amount of money that is stored in the contract.

```javascript
 mapping (address => uint) public AvailableBalance;
```
The mapping function is a function that stores the available balance of the respective address.
```javascript
    function mint(address WalletAddress, uint Amount) public  onlyOwner{
       AvailableBalance[WalletAddress] = AvailableBalance[WalletAddress] + Amount;
        TotalSupply = TotalSupply + Amount;
```
 The mint() function allows the owner of the contract to create new tokens and deposit them into a wallet address. The tokens after minting is added to the total supply of the token.
 ```javascript
  function burn(address WalletAddress, uint Amount) public {
        if (AvailableBalance[WalletAddress] >= Amount) {
            AvailableBalance[WalletAddress] = AvailableBalance[WalletAddress] - Amount;
            TotalSupply = TotalSupply - Amount;
```
The burn() function allows the owner of the contract to destroy tokens from a wallet address. If the specified wallet address has at least the specified amount of tokens, the burn() function will reduce the wallet address's available balance by the specified amount and reduce the total supply of tokens by the specified amount.
