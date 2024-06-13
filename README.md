# eth-beginer-project
// SPDX-License-Identifier: MIT
pragma solidity ^0.4.18;

contract MyToken {

    // Public variables to store the details about the coin
    string public name = "META";
    string public symbol = "MTA";
    uint256 public totalSupply;

    // Mapping to store balances of addresses
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    function mint(address _to, uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    // Burn function to destroy tokens
    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value);
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}

    
