# Thorchain

The real problem is that they need highly complex offchain processes -- the code linked in the article is in golang, and I guess the attacker was able to point it at their shady router to confuse it. This is common though because Ethereum is both so unsafe and so expensive that projects move everything they can off-chain, which is both centralized/non-transparent (off-chain) and additionally complex because now your offchain state is highly coupled with fragile on-chain state. Compare to the bridge relay where all inbound txs from Ethereum are processed on-chain, in Pact -- (a) the Pact code is far simpler meaning (b) the relay software is really simple.

Complex relays are a huge risk, whereas the bridge relay software is really just shuttling API calls and signing.

Software in general is dangerous. That's why we code in Haskell, not go, and Pact, not solidity -- the more restrictive, the better.

Also It's PoS which is inherently centralized, The Gauntlet's security analysis was bullish ... unless you read the fine print: "We also find the current distribution of the circulating RUNE supply of 160MM is suitable for initialization and the minimum bonding limit of 1MM keeps the bonded to staked ratio just above the optimal value of 2 with the caveat that they both need to be carefully monitored and may require future intervention ... Avoiding potential downward spirals like bonder plutocracy could still however require a combination of governance and benevolence."
