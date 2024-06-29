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
