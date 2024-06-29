# Hello World

This Solidity program is a simple "Hello World" program that demonstrates the basic syntax and functionality of the ERC20 contracts using  Solidity programming language. 

## Description

This program is a simple ERC20 contract written in Solidity . The contract has a mutiple functions. This program serves as a simple and straightforward introduction to ERC20 contracts using Solidity programming, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MToken.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.13;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract Mtoken is ERC20, Ownable {
    constructor(string memory name, string memory symbol) ERC20(name, symbol) Ownable(msg.sender) {
        // Mint 100 tokens to msg.sender (contract creator)
        _mint(msg.sender, 100 * 10 ** decimals());
    }

    // Function to mint new tokens (only owner can call this)
    function mint(address to, uint256 amount) public onlyOwner {
        _mint(to, amount);
    }

    // Function to burn tokens (any user can call this)
    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }

    // Transfer function is already inherited from ERC20, no need to define it again
}


```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile MToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint,burn and transfer functions . Click on the "MToken" contract in the left-hand sidebar, and then click on the "MINT" function similarly interact with the "BURN" function and "TRANSFER" function . 

## Authors

Shrey Dixit


## License

This project is licensed under the MIT License.
