    ID: 1
    Title: Validation of MinexBank address and commission
    Author: Roman Hulenko <rhulenko@minexsystems.com>
    Type: Standard
    Layer Consensus(Soft Fork)
    Status: Final
    Created: 2017-09-29

## Motivation
Consensus algorithm must validate MinexBank address and commission for сurrency volatility support, otherwise an attacker may disrupt the reliability of the currency.

## Rationale
Minex Bank commission calculated using only integer instead float point numbers to avoid inaccuracy problem. Consensus prohibits miner to burn coins to save a certain number of coins in the system. Each node must check that the second output of the coinbase transaction belongs to the MinexBank address and have a sufficient number of coins on the account. 

## Backwards Compatibility
It's soft fork, new rules are reinforced version of old rules. New consensus rules start on 24000 block height.

## Implementation
In minexcoin repository
https://github.com/minexcoin/minexcoin/commit/f3bd05d9078dc3a17c8a20a9df5a0bd7f2510d85,
https://github.com/minexcoin/minexcoin/commit/648feba72c162deb75f7c80524856743d63e8783.
