# MToken ERC20 based token for Metacrafter ETH + AVAX Module 3

The **MToken** smart contract is an ERC-20 token implementation. It allows for the creation of a custom token with the following features:

1. **Name and Symbol**: The token has a user-defined name and symbol.
2. **Initial Supply**: The contract creator (owner) is initially allocated 10 tokens.
3. **Minting**: The owner can mint additional tokens and allocate them to any address.
4. **Burning**: Any address can burn (destroy) their own tokens.
5. **Transfer**: Anyone can transfer his/her token holding.

## Usage

1. Deploy the contract, specifying the desired name and symbol.
2. The owner can mint new tokens using the `mint` function.
3. Users can transfer tokens.
4. To burn tokens, call the `burn` function.

## Functions

- `mint(address to, uint256 amount)`: Mint new tokens and allocate them to the specified address. Only the owner can call this function.
- `burn(uint256 amount)`: Burn (destroy) a specified amount of tokens from the caller's balance.
- `transfer(address reciever, uint amount)`: Any user can call this and transfer their token with others.
