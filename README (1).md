# Smart Contract -- MyToken

## Description

MyToken is an Ethereum-based smart contract written using Solidity programming language. This smart contract allows us to mint and burn tokens and helps us to track of the total supply of the tokens and also to map Address to Balanace.

## Contract Details

### Public Variables

- `TokenName`: The name of the token, here used as "JAY".
- `TokenAbr`: The abbreviation of the token, here used as "JP".
- `TokenSupply`: The total supply of the token, by default set to 0.

### Mapping

- `AddressToBalance`: A mapping that keeps track of each address's token balance.

### Functions

#### 1. mintToken

This function helps us to mint new tokens.

- **Parameters**:
  - `_address`: The address of the new tokens.
  - `_value`: The value of tokens to be added.

- **Logic**:
  - Increases the total supply by the passed value and balance of the specified address by the passed value.

```solidity
function mintToken(address _address, uint256 _value) public {
    TokenSupply += _value;
    AddressToBalance[_address] += _value;
}
```

#### 2. burnToken

This function helps us to burn the tokens.

- **Parameters**:
  - `_address`: The address of token to be burned.
  - `_value`: The value of token to be burned.

- **Logic**:
  - Checks if the specified address has enough balance to burn the tokens.
  - Decreases the total supply by the passed value and the balance of the specified address by the passed value, if the condition is satisfied.
  - Reverts the transaction if the balance is insufficient and the checked condition fails.

```solidity
function burnToken(address _address, uint256 _value) public {
    if (AddressToBalance[_address] >= _value) {
        TokenSupply -= _value;
        AddressToBalance[_address] -= _value;
    } else {
        revert("Insufficient Balance in Mapping Address account");
    }
}
```

## Deployment

To deploy the `MyToken` smart contract, we can use Remix IDE.

### Using Remix

1. Open [Remix](https://remix.ethereum.org/).
2. In the Contracts folder, create a new file and paste the contract code into the editor.
3. Compile the contract, using Ctrl+S.
4. Deploy the contract to the desired Ethereum network.
   
## License

This project is licensed under the MIT License - see the LICENSE.md file for details

## Authors

Gopavaram Jayaprakash Reddy

## Contributing

Contributions are welcome! Feel free for any changes or improvements.

---

This README provides a comprehensive guide to understanding, deploying, and using the `MyToken` smart contract.
