# Solidity Project Assessment

This Solidity program is a simple program that illustrates the basics of the Solidity programming language. Solidity project for Metacrafters.

## Description

This program is a simple contract written in Solidity. Solidity is a programming language that is utilitized for developing smart contracts on the Ethereum blockchain. The contract contains three public variables that store details about my coin: tokenName, tokenAbbrv, and totalSupply. The contract also contains a mapping of balances. The program also contains a mint and a burn function. Both functions take in two parameters: address and value. The mint function then increases the total supply by that number and increases the balance of the address by that amount. The burn function does the opposite and instead decreases the balance of the address while taking into account the value of the balance of the address and the value to be deducted. If the balance of the account is greater than the value to be deducted, the function will deduct the value form the balance. Otherwise, it will skip the code in the function and do nothing.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the code from the SolidityProject.sol file from the repository or the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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
    string public tokenName = "LEAGUE";
    string public tokenAbbrv = "LGE";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _val) public {
        totalSupply += _val;
        balances[_address] += _val;
    }

    // burn function
    function burn(address _address, uint _val) public {
        if(balances[_address] > _val){
            totalSupply -= _val;
            balances[_address] -= _val;
        }
        
    }
}

```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile SolidityProject.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "SolidityProject" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the all the functions and interacting with the variables.

# Authors

Allan C. Magtibay Jr.
