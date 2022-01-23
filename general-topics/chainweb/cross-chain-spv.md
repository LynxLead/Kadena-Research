# Cross chain / SPV

there isn't much too it so there's not much writing on it. It's just spv. The original chainweb paper has a section on it but that's about it. What are you looking for? That can help guide the search.

Normally, when people think about multiple chains and communication between them, they think about something like cosmos where messages need to be shuttled from region to region (and more shuttling equals more load equals less scaling). This isn't what chainweb does.

Cross chain interactions actually don't impact scalability. Scale comes from the braiding, which is done with headers, and so the braiding isn't effected at all by the existence or non existence of Cross chain transfers. Chains don't capture information directly to shuttle around to other chains. Instead, message passing is done with trustless Merkle proofs. Spv and Merkle proofs were one of Satoshi's coolest ideas but they never found adoption (people are fine running their own node or trusting an explorer to prove that a tx has gone through). We didn't invent them, just repurposed spv to empower a multi chain network to have zero cost (at the consensus level) Cross chain interactions.

I'm happy to walk you through the concept over the course of a couple days on here if needed. I'm not sure we know what we should be writing about the matter. Chainweb in general is a pretty simple structure, but has a lot of nuance in the implications.

For now, read up on simple payment verification in Bitcoin.

As for who can use this magic shuttle-less cross chain messaging system -- that'd be everyone writing pact on Kadena. It's a user-level piece of infra, that will allow dapp devs to shard their dapp across multiple chains for scaling purposes. It takes about 50 lines of pact to make a pact contract, uh, shard-able? scale-able? partition-able? Dunno if this has ever been doable before so we may need to coin a phrase for it (so it doesn't get confused with layer-2 tricks).

***

The origin story for kadena's scaling approach (chainweb) came out of SPV research, so SPV is at the core of it all. I've also never seen anything else even close to it -- cross chain stuff normally needs an oracle or relay network, which means that cross chain txs induce load somewhere besides the tx ledger.

SPV let's us piggy-back the TX's "chatter" on the merkle structure of the blockchain itself. First, the braid structure enforces causality for cross-chain txs (a reorg that removes the burn step must also have reorged the create and thus force re-evaluation). This allows us to trust that a successful create can only exist if the paired burn occurred upstream in the network. Then, the proofs themselves that are constructed off of create are cryptographic proofs... so an attacker would need to collide a hash to successfully fake a create. These two parts, when paired together, mean that the ledgers for the create side and the burn side don't "pass a message". Instead the "sending" chain's ledger records a burn receipt and the "receiving" chain validates the cryptographic evidence that the burn occurred... but the chains never actually "reach beyond" their ledger's state.

The approach isn't limited to burn/create either -- any information that can be recorded as a receipt can have an SPV drawn to it for other chains to consume.

***

Motivating general example: say you have a DAO that has scaled to span 5 chains and has a decentralized governance mechanism built in. You can't really coordinate voting on each of the 5 contracts (1 per chain). Instead, you'd designate 1 contract where the vote happens on upgrades and have the other 4 contracts have their governance dictated by the governance of the designated contract. SPV/cross-chain lets the results of the vote and the upgrade commands be transmitted cross-chain.
