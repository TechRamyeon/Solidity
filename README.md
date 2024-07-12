# Solidity

## MyToken Contract

### Overview

The MyToken contract is a simple ERC-20 like token implementation in Solidity. This smart contract allows for minting and burning of tokens. It includes public variables to store token details and mappings to keep track of balances. Below is a detailed description of the contract's functionality and how to use it.

Requirements
Public Variables:

tokenName: Stores the name of the token.
tokenAbbrv: Stores the abbreviation of the token.
totalSupply: Stores the total supply of the token.
Mappings:

balances: Maps addresses to their respective token balances.
Functions:

mint: Increases the total supply and the balance of a specified address.
burn: Decreases the total supply and the balance of a specified address, ensuring the address has enough balance to burn.
Contract Details
Public Variables
```string public tokenName = "EMIRU";```

The name of the token.
```string public tokenAbbrv = "EMI";```

The abbreviation of the token.
```uint public totalSupply = 0;```

The total supply of the token.
Mappings
```mapping(address => uint) public balances;```
This mapping keeps track of each address's token balance.
Functions

Mint
```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```
Parameters:
_address: The address to which tokens will be minted.
_value: The number of tokens to mint.

Functionality:
Increases the totalSupply by _value.
Increases the balance of _address by _value.

Burn
```solidity
function burn(address _address, uint _value) public {
    if(balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```
Parameters:
_address: The address from which tokens will be burned.
_value: The number of tokens to burn.
Functionality:

Checks if the balance of _address is greater than or equal to _value.
If true, decreases the totalSupply by _value.
Decreases the balance of _address by _value.
Usage

Deploying the Contract:
Deploy the MyToken contract to your preferred Ethereum network.

Minting Tokens:
Call the mint function with the desired address and value to increase the total supply and the balance of the specified address.

Burning Tokens:
Call the burn function with the desired address and value to decrease the total supply and the balance of the specified address, provided the address has enough balance.

Example
Minting 100 tokens to address 0x123...789:

```solidity
mint(0x1234567890abcdef1234567890abcdef12345678, 100);

burn(0x1234567890abcdef1234567890abcdef12345678, 50);
```
## License
This project is licensed under the MIT License.


// SPDX-License-Identifier: MIT
