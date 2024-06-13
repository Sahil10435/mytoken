// SPDX-License-Identifier: MIT
pragma solidity 0.8.0;
contract MyToken {
    string public tokenName;
    string public Abbrv;
    uint256 public totalSupply;

    mapping(address => uint256) public addressBalances;

    constructor(string memory _name, string memory _abbrv, uint256 _initialSupply) {
        tokenName = _name;
        Abbrv = _abbrv;
        totalSupply = _initialSupply;
        addressBalances[msg.sender] = _initialSupply;
    }

    function mint(address _recipient, uint256 _value) public {
        totalSupply += _value;
        addressBalances[_recipient] += _value;
    }

    function burn(address _account, uint256 _value) public {
        require(addressBalances[_account] >= _value, "LOW balance");
        totalSupply -= _value;
        addressBalances[_account] -= _value;
    }
}
