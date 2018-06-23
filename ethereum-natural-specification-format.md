<!-- TITLE: Ethereum Natural Specification Format -->



Solidity contracts can have a special form of comments that form the basis of the Ethereum Natural Specification Format. For a usage example please check [here](http://wikijs.ethereum.wiki/Natspec-Example/).

# Documentation Example

Documentation is inserted above the function following the doxygen notation of either one or multiple lines starting with `///` or a multiline comment starting with `/**` and ending with `*/`.

This example shows a contract and a function using all available tags. Note: NatSpec currently does NOT apply to variables (see [solidity#3418](https://github.com/ethereum/solidity/issues/3418)), even if they are declared public and therefore do affect ABI. Note: NatSpec currently only interprets tags functions if they are external or public. You are welcome to use similar comments for your internal and private functions, but those will not be parsed.

```solidity
pragma solidity ^0.4.19;

/// @title A simulator for Bug Bunny, the most famous Rabbit
/// @author Warned Bros
/// @notice You can use this contract for only the most basic simulation
/// @dev All function calls are currently implement without side effects
contract BugsBunny {
    /// @author Bob Clampett
    /// @notice Determine if Bugs will accept `(_food)` to eat
    /// @dev String comparison may be inefficient
    /// @param _food The name of a food to evaluate (English)
    /// @return true if Bugs will eat it, false otherwise
    function doesEat(string _food) external pure returns (bool) {
        return keccak256(_food) == keccak256("carrot");
    }
}
```

# Tags

All tags are optional. The following table explains the purpose of each NatSpec tag and where it may be used.

| Tag       |                                          | Context                       |
| --------- | ---------------------------------------- | ----------------------------- |
| `@title`  | A title that should describe the contract | contract, interface           |
| `@author` | The name of the author of the contract   | contract, interface, function |
| `@notice` | Explain to a user what a function does   | contract, interface, function |
| `@dev`    | Explain to a developer any extra details | contract, interface, function |
| `@param`  | Documents a parameter just like in doxygen (must be followed by parameter name) | function                      |
| `@return` | Documents the return type of a contract's function | function                      |

## Dynamic expressions

In function documentation, you may use dynamic expressions for all tags. Example:

    /// @notice Send `(valueInmGAV / 1000).fixed(0,3)` GAV from the account of 
    /// `message.caller.address()` to an account accessible only by `to.address()`
    function send(address to, uint256 valueInmGAV) {
    ...

If a user (address 0x2334) attempts to call this function with a `to` address of `0x0` and `valueInmGAV` of 4,135 then this will render to the user as:

 > Send 4.135 GAV from the account of 0.2334 to an account accessible only by 0x0

Use any Javascript/Paperscript expression encapsulated in backticks as per the above example. This script will be run on a EVM Javascript environment that has access to `message` and all parameters.

## Notes

Currently it is undefined whether a contract with a function having no NatSpec will inherit the NatSpec of a parent contract/interface for that same function.

# Documentation Output

When parsed, documentation such as the one from the above example will produce 2 different json files. One is meant to be consumed by the user as a notice when a function is executed and the other to be used by the developer.

Let us see a more full contract example.

```
/// @title This is the contract title.
/// @author Homer Simpson
contract GavCoin
{
  /// @notice Send `(valueInmGAV / 1000).fixed(0,3)` GAV from the account of 
  /// `message.caller.address()`, to an account accessible only by `to.address()
  /// @dev This should be the documentation of the function for the developer docs
  /// @param to The address of the recipient of the GavCoin
  /// @param valueInmGav The GavCoin value to send
  function send(address to, uint256 valueInmGAV) {
    if (balances[msg.sender] >= valueInmGAV) {
      balances[to] += valueInmGAV;
      balances[msg.sender] -= valueInmGAV;
    }
  }

  /// @notice `(balanceInmGAV / 1000).fixed(0,3)` GAV is the total funds available to `who.address()`.
  /// @param who The address of the person whose balance we check
  /// @return The balance of the user provided as argument
  function balance(address who) constant returns (uint256 balanceInmGAV) {
    balanceInmGAV = balances[who];
  }

  mapping (address => uint256) balances;
}
```

## User Documentation

The above documentation will produce the following user documentation json file as output:

```
{
  "source": "...",
  "language": "Solidity",
  "languageVersion": 1,
  "methods": {
    "send(address,uint256)": { "notice": "Send `(valueInmGAV / 1000).fixed(0,3)` GAV from the account of `message.caller.address()`, to an account accessible only by `to.address()`." },
    "balance(address)": { "notice": "`(balanceInmGAV / 1000).fixed(0,3)` GAV is the total funds available to `who.address()`." }
  },
  "invariants": [
    { "notice": "The sum total amount of GAV in the system is 1 million." }
  ],
  "construction": [
    { "notice": "Endows `message.caller.address()` with 1m GAV." }
  ]
}
```

Note that the key by which to find the methods is the function's canonical signature as defined in the [Contract ABI](http://wikijs.ethereum.wiki/Ethereum-Contract-ABI#signature) and not simply the function's name.

## Developer Documentation

Apart from the user documentation file, a developer documentation json file should also be produced and should look like this:

```
{
  "author": "Homer Simpson",
  "title": "This is the contract title.",
  "methods": {
    "send(uint256)": {
      "details": "This should be the documentation of the function for the developer docs"
    },
    "balance": {
      "details": ""
    }
  },
  "invariants": [
     { "details": "This is the invariant development documentation"}
  ],
  "construction": {
     "details": ""
  }
}
```

## Example usage

There is a detailed example of using the Natspec feature with the cpp client [here](http://wikijs.ethereum.wiki/Natspec-Example/).