# Major issues resulting in lost or stuck funds

Ethereum has had expensive bugs, such as the following:

## The DAO

**3,600,000 ETH stolen** (recovered through hard fork)

To read about [the DAO vulnerability](https://en.wikipedia.org/wiki/The_DAO_(organization)), press <kbd>CTRL</kbd> + <kbd>f</kbd> in the linked Wikipedia article and search for vulnerability.

## Ethereum Classic replay attacks

Ethereum Classic replay attacks also occurred ensuing the DAO hard fork, which were subsequently fixed by [EIP-155](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-155.md).

## Parity multisig library contract issues 1

\[[1](https://paritytech.io/the-multi-sig-hack-a-postmortem/), [2](https://paritytech.io/security-alert/), [3](https://paritytech.io/security-update/)] 

**153,037 ETH stolen**

The first Parity multisig library bug was fixed in [this pull request](https://github.com/paritytech/parity/pull/6103/files). 

> On Wednesday 19th July, 2017 a bug found in the multi-signature wallet ("multi-sig") code used as part of Parity Wallet software was exploited by parties unknown... The bug was in a pair of extremely sensitive functions designed to allow the set-up of "multi-sig" wallets in the Parity Wallet software. The functions should have been protected in order that they be usable only in one specific circumstance, as the contract was being created. However, they were entirely unguarded, which allowed the attacker to reset the ownership and usage parameters of existing wallets arbitrarily.

## Parity multisig library contract issue 2

\[[4](https://paritytech.io/security-alert-2/), [5](https://paritytech.io/parity-technologies-multi-sig-wallet-issue-update/), [6](https://paritytech.io/a-postmortem-on-the-parity-multi-sig-library-self-destruct/), [7](https://paritytech.io/on-classes-of-stuck-ether-and-potential-solutions/)] 

**513,736 ETH stuck**

> Following the fix for the <a href="https://paritytech.io/blog/security-alert-high-2.html">original multi-sig vulnerability</a> that had been exploited on 19th of July (function visibility), a new version of the Parity Wallet library contract was deployed on 20th of July. Unfortunately, that code contained another vulnerability which was undiscovered at the time - it was possible to turn the Parity Wallet library contract into a regular multi-sig wallet and become an owner of it by calling the initWallet function. It is our current understanding that this vulnerability <a href="https://github.com/paritytech/parity/issues/6995">was triggered</a> accidentally on 6th Nov 2017 02:33:47 PM +UTC and subsequently a user deleted the <a href="https://etherscan.io/address/0x863df6bfa4469f3ead0be8f9f2aae51c91a907b4">library-turned-into-wallet</a>, wiping out the library code which in turn rendered all multi-sig contracts unusable and funds frozen since their logic (any state-modifying function) was inside the library.

> All dependent multi-sig wallets that were deployed after 20th July functionally now look as follows:

```solidity
contract Wallet {
    function () payable {
    Deposit(...)
    }
}
```

> This means that currently no funds can be moved out of the multi-sig wallets.

## Cases covered in [EIP-156](https://github.com/ethereum/EIPs/issues/156)

(We should split these out and have a section for each distinct issue)

EIP-156 gives more examples such as sending to an empty address, e.g. [1](https://github.com/ethereum/EIPs/issues/156#issuecomment-2766829920) and [2](https://github.com/ethereum/EIPs/issues/156#issuecomment-307015852).

## "0x" prefix enforcement (QuadrigaCX)

**67,317 ETH stuck**

(this is my understanding, needs to be verified) 

QuadrigaCX attempted to send funds shortly after Ethereum switched over to require the "0x" prefix. Quadriga's sweeper daemon attempted to collect funds from deposit accounts and then send them through the `SafeConditionalHFTransfer` contract to their collection account.  However, the sweeper daemon did not include the "0x" prefix on addresses which resulted in malformed input sent to the contract.  The contract's fallback function was invoked which had no default logic.  The contract does not include any mechanism to retrieve ETH (or tokens) sent to it.

<https://github.com/bokkypoobah/BadBeef/blob/master/README.md>  
<https://www.reddit.com/r/ethereum/comments/6ettq5/statement_on_quadrigacx_ether_contract_error/>

Contract with stuck funds: <https://etherscan.io/address/0x1e143b2588705dfea63a17f2032ca123df995ce0#code>.  
Presumably, more than just QuadrigaCX is affected.  

## EthereumJS Padding Bug

(this is my understanding, needs to be verified)

A bug in EthereumJS caused the public key to be incorrectly computed from the private key.  So, users created an account and the utility would generate an address. However, it was not the address that corresponded to the private key.  

Sources are e.g. [here](https://forum.ethereum.org/discussion/3988/bug-in-ethereumjs-util) and [here](https://www.reddit.com/r/ethereum/comments/6chqyk/trying_to_recover_my_121_eth_from_2015_js_bug/).

## REXmls

**6687 ETH stuck**

During deployment of the contract, the address for the "vault" wallet was incorrectly specified.  From the blog post: "Instead of a quoted string for an address, a Javascript hex string was used".  When participants contributed, they received tokens, but the crowdsale contract forwarded ETH to the wrong address.

Contract: <https://etherscan.io/address/0x03e4b00b607d0980668ca6e50201576b00000000>.  
Issue: <https://blog.rexmls.com/the-solution-a2eddbda1a5d>.

## Off By One

An address received ETH which has no transaction history and is exactly 1 byte off from an address that does have a transaction history.  We can assert that it is unreasonably improbable that there are two private keys that have a public address that are within 1 byte of each other, one of which has never been used and the other which has.

This problem occurs when a user accidentally typos address entry when sending (e.g., accidentally changes the last character of the address).

## Contracts Deployed With No Code

When a user submits a transaction with no `to` field, it is interpreted as a contract deployment.  If they also leave out the `data` field this results in a contract being deployed with no code.  If the transaction has ETH attached to it then the ETH becomes inaccessible as it is given to the "contract" even though the contract has no code associated with it.  This problem most commonly occurs when someone constructs a transaction incorrectly (accidentally leaving off the `to` field) but can also occur when someone attempts to create a contract but accidentally leaves out the data.  In either case, it is easy to identify and the proper owner is obvious (transaction submitter).

An example of this bug biting a user can be seen here: <https://github.com/ethereum/go-ethereum/issues/15639>
