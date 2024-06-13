# MyToken

This Solidity program is a simple token contract that demonstrates the basic functionality of a custom token on the Ethereum blockchain. The purpose of this program is to provide a starting point for those who are new to Solidity and want to understand how to create and manage tokens.

## Description

This contract is written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract includes functionality to mint and burn tokens, manage balances, and track the total supply of the token.

## Features

1. **Public Variables**: The contract has public variables to store the token's name, abbreviation, and total supply.
2. **Mapping**: The contract includes a mapping to track balances associated with each address.
3. **Mint Function**: Allows tokens to be created and added to the total supply.
4. **Burn Function**: Allows tokens to be destroyed and removed from the total supply, with checks to ensure sufficient balance.

## Getting Started

### Executing the Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix IDE](https://remix.ethereum.org/).

1. **Create a New File**:
   - Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar.
   - Save the file with a `.sol` extension (e.g., `MyToken.sol`).

2. **Write the Code**:
   - Write the following code into the file:

     ```solidity
     // SPDX-License-Identifier: MIT
     pragma solidity ^0.8.26;

     contract MyToken {
         // Public variables here
         string public tokenName = "priyanka";
         string public tokenAbrev = "MTA";
         uint public totalSupply = 0;

         // Mapping variable here
         mapping(address => uint) public balance;

         // Mint function
         function mint(address _address, uint _value) public {
             totalSupply += _value;
             balance[_address] += _value;
         }

         // Burn function
         function burn(address _address, uint _value) public {
             if (balance[_address] >= _value) {
                 totalSupply -= _value;
                 balance[_address] -= _value;
             }
         }
     }
     ```

3. **Compile the Code**:
   - Click on the "Solidity Compiler" tab in the left-hand sidebar.
   - Make sure the "Compiler" option is set to "0.8.26" (or another compatible version), and then click on the "Compile MyToken.sol" button.

4. **Deploy the Contract**:
   - Once the code is compiled, click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
   - Select the "MyToken" contract from the dropdown menu.
   - Click on the "Deploy" button.

5. **Interact with the Contract**:
   - Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions.
   - To mint tokens, use the `mint` function with the desired address and value.
     ```solidity
     mint(0xYourAddress, 100);
     ```
   - To burn tokens, use the `burn` function with the desired address and value.
     ```solidity
     burn(0xYourAddress, 50);
     ```

## Authors

- Priyanka Barman [@Barmanpriyanka](https://github.com/Barmanpriyanka)

## License

This project is licensed under the MIT License - see the LICENSE file for details.

