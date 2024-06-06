# Project: Create a Token

## Description

The provided Solidity contract, named MyToken, implements a simple token system with essential functionalities for minting and burning tokens. It defines three public variables: name, set to "META", representing the token's name; symbol, set to "MTA", representing the token's abbreviation; and totalSupply, initialized to 0, representing the total supply of the tokens. The contract also includes a public mapping called balances to keep track of the token balances for each address. The mint function allows the creation of new tokens by increasing the totalSupply and updating the balance of a specified address. Conversely, the burn function enables the destruction of tokens by reducing the totalSupply and the balance of a specified address, but only if the address has sufficient tokens to burn. This ensures that tokens can only be burned if the address holds enough balance, maintaining the integrity of the token supply.

## Getting Started

### Executing program

1. License and Solidity Version:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

```
- // SPDX-License-Identifier: MIT: This line specifies the license type for the contract, which is MIT in this case.
- pragma solidity 0.8.25;: This line specifies the version of the Solidity compiler to be used, which is 0.8.25.

2. Contract Definition:

```solidity
contract MyToken {

```
-This line starts the definition of the contract named MyToken.

3. Public Variables:

```solidity
string public name = "META";
string public symbol = "MTA";
uint256 public totalSupply = 0;

```
- name: A public string variable to store the name of the token, set to "META".
- symbol: A public string variable to store the abbreviation (symbol) of the token, set to "MTA".
- totalSupply: A public unsigned integer variable to store the total supply of the token, initialized to 0.

4. Mapping for Balances:

```solidity
mapping(address => uint256) public balances;

```
-This creates a public mapping that associates each address with its balance of tokens.

5. Mint Function:

```solidity
function mint(address _to, uint256 _amount) public {
    totalSupply += _amount;
    balances[_to] += _amount;
}

```
- mint: A public function that takes two parameters: _to (the address to mint tokens to) and _amount (the amount of tokens to mint).
- Inside the function:
  * totalSupply += _amount;: Increases the total supply of the token by the specified amount.
  * balances[_to] += _amount;: Increases the balance of the specified address by the same amount.

6. Burn Function:

```solidity
function burn(address _from, uint256 _amount) public {
    if (balances[_from] >= _amount) {
        totalSupply -= _amount;
        balances[_from] -= _amount;
    }
}

```
- burn: A public function that takes two parameters: _from (the address to burn tokens from) and _amount (the amount of tokens to burn).
- Inside the function:
  * if (balances[_from] >= _amount): Checks if the balance of the specified address is greater than or equal to the amount to be burned.
  * If the condition is true:
    - totalSupply -= _amount;: Decreases the total supply of the token by the specified amount.
    - balances[_from] -= _amount;: Decreases the balance of the specified address by the same amount.


## Authors

Milan


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
