# Ethereum

* Bitcoin was the first implementation of a decentralized currency, using a distributed consesus algorithm called 'proof of work'
* POW solved 2 problems:
  1. provides a simple and effective consensus algorithm
  2. provides a mechanism for free entry into the consensus process
* alternative to POW is 'proof of stake'

## Bitcoin as a State Transition System

* `APPLY(S,TX) -> S' or ERROR`, where S is current state and TX is a transition
* state is not explicitly stored, but rather implied from the chain of transitions

## Merkle Trees

* Tree data structure where the values we want to store are stored only in leaf nodes, and each non-leaf node's value is the hash of its two children nodes
* Thus, you can verify the integrity of the entire tree by just checking the root hash
* Piecewise verification is also possible

## Ethereum accounts

* The state is made up of objects called accounts
* Each account has a 20-byte address, and contains 4 fields
  1. Nonce, a counter used to make sure each transaction is only processed once
  2. Current ether balance
  3. Account's contract code
  4. Account's storage
* Accounts can be either externally owned accounts or contract accounts

## Ether

* Main internal crypto-fuel of Ethereum, used to pay transaction fees
