# Bridge

Kadena is really focusing on non-interactive decentralized bridges. Right now, much of defi "bridges" are just bots shuttling between chains... which are both a reg nightmare and a security hole. They are going the other way, with SPV/Merkle proofs at the core. In that, they have an advantage, because cross-chain SPV is already designed into the platform... it was needed to allow chainweb to work and scale

Decentralized bridges need to validate hashes on-chain. This is part of why there are no fully decentralized bridges to ETH in existence. Centralized bridges are nice until they suffer the same fates as centralized exchanges and get hacked.

There are different grades of "decentralization" for bridges. A "fully" decentralized bridge would be based on PoW witnesses. In order to validate those one has to check PoW hashes. A good/efficient PoW hash function (which kadena is using) requires very little resources for validation of a PoW hash (because GPU algos tend to make fully decentralized bridges more difficult.)

Kadena is using decentralized header oracles instead of running native POW hashes in Solidity Bonding secures the bridge -- bonders "endorse" cryptographic data coming from Ethereum, putting their bond at risk of being slashed. The good news is that it's not an interactive system, technically speaking. So if you're offline for a bit, you won't be punished, unless you're so offline that you never do anything. All of the techniques used for the Eth bridge (bonding, endorsement, dao, wrapping, registration) will be used, for Celo almost identically, for Terra/Cosmos only the endorsement and wrapping change.

***

#### Why thorchain is centralized

The real problem is that they need highly complex offchain processes -- the code linked in the article is in golang, and I guess the attacker was able to point it at their shady router to confuse it. This is common though because Ethereum is both so unsafe and so expensive that projects move everything they can off-chain, which is both centralized/non-transparent (off-chain) and additionally complex because now your offchain state is highly coupled with fragile on-chain state. Compare to the bridge relay where all inbound txs from Ethereum are processed on-chain, in Pact -- (a) the Pact code is far simpler meaning (b) the relay software is really simple.

Complex relays are a huge risk, whereas the bridge relay software is really just shuttling API calls and signing.

Software in general is dangerous. That's why we code in Haskell, not go, and Pact, not solidity -- the more restrictive, the better.

Also It's PoS which is inherently centralized, The Gauntlet's security analysis was bullish ... unless you read the fine print: "We also find the current distribution of the circulating RUNE supply of 160MM is suitable for initialization and the minimum bonding limit of 1MM keeps the bonded to staked ratio just above the optimal value of 2 with the caveat that they both need to be carefully monitored and may require future intervention ... Avoiding potential downward spirals like bonder plutocracy could still however require a combination of governance and benevolence."

***

Yes, both technically (we're using decentralized header oracles instead of running native POW hashes in Solidity) and economically -- our bridge relay program will incentivize participants to post headers, which includes covering gas fees.
