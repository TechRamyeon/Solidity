MyToken Smart Contract
This is a simple ERC-20 token smart contract written in Solidity.

Features
Stores token details: name, abbreviation, and total supply.
Tracks individual user balances using a mapping.
Provides functions for minting and burning tokens.
Requirements
Solidity compiler version ^0.8.18 or later.
Deployment
Compile the contract using solc MyToken.sol.
Deploy the contract to your preferred blockchain network.
Usage
Minting:

Use the mint function to create new tokens and assign them to an address.

Solidity
contract MyContract {
  function someFunction() public {
    MyToken token = new MyToken();
    token.mint(msg.sender, 100); // Mint 100 tokens to the sender address
  }
}

content_copy
Burning:

Use the burn function to destroy existing tokens from an address.

Solidity
contract MyContract {
  function someFunction() public {
    MyToken token = new MyToken();
    token.burn(msg.sender, 50); // Burn 50 tokens from the sender address
  }
}

content_copy
Important Note:

The burn function includes a safety check to ensure the sender has enough balance before burning tokens.

License
This contract is licensed under the MIT License.
