
# ETH PROOF: Beginner EVM Course Project

A repository for developing and showcasing various smart contracts written in Solidity, aimed at helping developers learn and implement blockchain solutions on Ethereum.

## Description

This repository is for my submission in metacrafters - ETH PROOF: Beginner EVM Course which focused on the development of smart contracts using the Solidity programming language. This repository includes various smart contracts, examples, and tools to help developers get started with Ethereum blockchain development. 

## Getting Started

### Installing

* Clone the repo from GitHub
   git clone https://github.com/nnerr/solidityy.git
   
* Install dependencies

   npm install
   
### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., Nerz.sol). Copy and paste the following code into the file:
  ```sh
  pragma solidity 0.8.26;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "Nerz";
    string public tokenAbbrv = "Nrz";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
        function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
}

  ```
## Help

Any advice for common problems or issues.
```sh
npx hardhat help
```

## Authors

Contributors names and contact info

Jonner Villapando

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
