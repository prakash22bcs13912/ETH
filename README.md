# MyToken Project

## Description
The MyToken project is a simple implementation of a basic ERC-20 token on the Ethereum blockchain. It demonstrates the fundamental functionalities of a cryptocurrency token, such as minting new tokens to an address and burning tokens from an address. This project serves as an educational resource for those new to blockchain development and smart contracts.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

# License-Identifier: MIT                                                                                                                                        
pragma solidity 0.8.18;

contract MyToken {

 ## Public variables to store the details about the coin
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint public totalSupply = 0;

 ## Mapping of addresses to balances
    mapping(address => uint) public balances;
    
    // Mint function to increase the total supply and balance of the "sender" address
    function mint(address _to, uint _value) 
    public 
    {
            totalSupply += _value;
            balances[_to] += _value;
    }

## Burn function to decrease the total supply and balance of the "sender" address
    function burn(address _from, uint _value) public 
        {
        require(balances[_from] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}

'''

Click on the "Solidity Compiler" tab in the left-hand sidebar.
Make sure the "Compiler" option is set to 0.8.18 (or another compatible version), and then click on the "Compile MyToken.sol" button.

## Authors
Gopavaram Jayaprakash Reddy

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
