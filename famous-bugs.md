# Famous Bugs

Bugs that resulted in lost or stuck funds have been moved to here: <https://github.com/ethereum/wiki/wiki/Major-issues-resulting-in-lost-or-stuck-funds>

## Geth Consensus Bug

> On 2016-11-24, a consensus bug occurred due to two implementations having different behavior in the case of state reverts. [3](https://blog.ethereum.org/2016/11/25/security-alert-11242016-consensus-bug-geth-v1-4-19-v1-5-2/). The specification was amended to clarify that empty account deletions are reverted when the state is reverted... Details: Geth was failing to revert empty account deletions when the transaction causing the deletions of empty accounts ended with an an out-of-gas exception. An additional issue was found in Parity, where the Parity client incorrectly failed to revert empty account deletions in a more limited set of contexts involving out-of-gas calls to precompiled contracts; the new Geth behavior matches Parity’s, and empty accounts will cease to be a source of concern in general in about one week once the state clearing process finishes. [The source is here.](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-161.md#addendum-2017-08-15)
