# MToken - ERC20 Token for Metacrafter ETH + AVAX Module 3

The **MToken** smart contract is an implementation of the ERC-20 standard, enabling the creation and management of a custom token with essential features. This contract serves as a versatile tool for developers looking to issue tokens on the Ethereum and Avalanche networks.

## Description

MToken provides a robust framework for creating and managing an ERC-20 token, complete with functionalities such as minting, burning, and transferring tokens. With an initial supply allocated to the contract owner, the MToken contract empowers users to interact with their tokens seamlessly.

### Features

1. **Name and Symbol**: Customizable name and symbol for your token.
2. **Initial Supply**: The contract owner starts with 10 tokens.
3. **Minting**: The owner can mint new tokens and allocate them to any address.
4. **Burning**: Users can burn their tokens, reducing the total supply.
5. **Transfer**: Users can easily transfer their token holdings.

## Getting Started

### Executing the Program

To deploy the MToken contract, you can use Remix, an online Solidity IDE. Follow these steps:

1. Go to the Remix website: [https://remix.ethereum.org/](https://remix.ethereum.org/).
2. Create a new file by clicking on the "+" icon in the left-hand sidebar. Save it with a `.sol` extension (e.g., `MToken.sol`).
3. Copy and paste the following code into the file:

   ```solidity
   // SPDX-License-Identifier: MIT
   pragma solidity ^0.8.4;

   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
   import "@openzeppelin/contracts/access/Ownable.sol";

   contract MToken is ERC20, Ownable {
       constructor(string memory name, string memory symbol) ERC20(name, symbol) {
           _mint(msg.sender, 10 * 10 ** decimals()); // Initial supply of 10 tokens
       }

       function mint(address to, uint256 amount) public onlyOwner {
           _mint(to, amount);
       }

       function burn(uint256 amount) public {
           _burn(msg.sender, amount);
       }
   }
## Compiling the Code

1. Click on the "Solidity Compiler" tab in the left-hand sidebar.
2. Ensure the "Compiler" option is set to "0.8.4" (or a compatible version).
3. Click on the "Compile MToken.sol" button.

## Deploying the Contract

1. Navigate to the "Deploy & Run Transactions" tab.
2. Select the MToken contract from the dropdown menu.
3. Enter the desired name and symbol for your token in the deployment inputs.
4. Click on the "Deploy" button.

## Interacting with the Contract

After deploying the contract, you can use the following functions:

- **Mint Tokens**: The owner can mint new tokens using the `mint(address to, uint256 amount)` function.
- **Burn Tokens**: Any user can burn their tokens by calling the `burn(uint256 amount)` function.
- **Transfer Tokens**: Users can transfer tokens to others using the standard `transfer(address recipient, uint256 amount)` function.


## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
