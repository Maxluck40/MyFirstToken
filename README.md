# MyFirstToken
This Solidity program is a basic implementation of an ERC20-like token. The purpose of this program is to demonstrate the creation and management of a simple token, including functionalities for minting and burning tokens. It serves as a starting point for those who are new to Solidity and want to learn how to create and manage their own tokens on the Ethereum blockchain.

## Description
This program is a smart contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract stores details about the token, such as its name, abbreviation, and total supply. It also maintains a mapping of addresses to balances and includes functions for minting new tokens and burning existing tokens. The mint function increases the total supply and the balance of a specified address, while the burn function decreases the total supply and the balance of a specified address, with checks to ensure sufficient balance.

## Getting Started

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at [Remix Ethereum](https://remix.ethereum.org/).

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a `.sol` extension (e.g., `MyFirstToken.sol`). Copy and paste the following code into the file:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyFirstToken {
    string public name;
    string public symbol;
    uint public totalSupply;

    mapping(address => uint) public balances;

    constructor(string memory _name, string memory _symbol, uint _initialSupply) {
        name = _name;
        symbol = _symbol;
        mint(msg.sender, _initialSupply);
    }

    function mint(address to, uint amount) public {
        totalSupply += amount;
        balances[to] += amount;
    }

    function burn(address from, uint amount) public {
        require(balances[from] >= amount, "Insufficient balance to burn");
        totalSupply -= amount;
        balances[from] -= amount;
    }
}
```

### Compiling and Deploying
1. **Compile the code:**
   - Click on the "Solidity Compiler" tab in the left-hand sidebar.
   - Make sure the "Compiler" option is set to "0.8.26" (or another compatible version).
   - Click on the "Compile MyFirstToken.sol" button.

2. **Deploy the contract:**
   - Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
   - Select the "MyFirstToken" contract from the dropdown menu.
   - Enter the required constructor parameters (Token Name, Token Abbreviation, Initial Supply).
   - Click on the "Deploy" button.

### Interacting with the Contract
Once the contract is deployed, you can interact with it using the following steps:

1. **Mint Tokens:**
   - Click on the deployed "MyFirstToken" contract in the left-hand sidebar.
   - Expand the "mint" function.
   - Enter the address and the amount of tokens to mint.
   - Click on the "transact" button.

2. **Burn Tokens:**
   - Click on the deployed "MyFirstToken" contract in the left-hand sidebar.
   - Expand the "burn" function.
   - Enter the address and the amount of tokens to burn.
   - Click on the "transact" button.

3. **Check Balances:**
   - Use the "balances" mapping to check the token balance of any address by entering the address and clicking on the "call" button.

## Authors
- Dennis Maxwell
  - GitHub: [@maxluck40](https://github.com/maxluck40)


## License
This project is licensed under the MIT License - see the LICENSE.md file for details
