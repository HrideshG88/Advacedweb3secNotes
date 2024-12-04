#Description: Frontrunning notes

# Frontrunning Attacks

## Mempool

A pool of Transactions yet to be finalized in a block.
Order of transactions in a pool can be arbitrary.
Tx can be prioritized to finalized by paying higher gas fees.

## Root cause

Order of transactions minted in the block is not sequentially related to their appearance in the pool hence situations can arise where executing tx before someone elses can lead to profit/griefing.

## Reports

### reward compounds are sandwichable

### Bad Actor can grief honest user by preventing orders from being created

## How to Find

- look for stepwise changes in balance of things that are assured
  - stepwise jump in woth of a token
  - jumps the amount of assets in a vault
- Look for What variables can change that can adversely affect the Tx
  - how would attacker benefit from this state change.
