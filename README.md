# Solidity Function Profiler

A command line tool that generates a human-consumable report listing a contract's functions. This is useful during manual code review to understand what functions are made public, use which modifiers, and so on.

Usage Example:

```
$ npm install
...
$ node index.js ~/contracts/mytoken.sol
```

|  Contract  |               Function                | Visibility | Constant | Returns |           Modifiers            |                Static Ana
         |      Coverage      | Func Ana |
|------------|---------------------------------------|------------|----------|---------|--------------------------------|-------------------------------------------|--------------------|----------|
| SmartToken | SmartToken(string,string,uint8)       | public     | false    |         | ERC20Token                     | :white_check_mark::ballot_box_with_check: | :white_check_mark: |          |
| SmartToken | disableTransfers(bool)                | public     | false    |         | ownerOnly                      | :white_check_mark::ballot_box_with_check: | :white_check_mark: |          |
| SmartToken | issue(address,uint256)                | public     | false    |         | ownerOnly,validAddress,notThis | :white_check_mark::ballot_box_with_check: | :white_check_mark: |          |
| SmartToken | destroy(address,uint256)              | public     | false    |         |                                | :white_check_mark::ballot_box_with_check: | :white_check_mark: |          |
| SmartToken | transfer(address,uint256)             | public     | false    | success | transfersAllowed               | :white_check_mark::ballot_box_with_check: | :white_check_mark: |          |
| SmartToken | transferFrom(address,address,uint256) | public     | false    | success | transfersAllowed               | :white_check_mark::ballot_box_with_check: | :white_check_mark: |          |

