---
description: disk space
---

# State Size Problem



> Will amount of data be a problem for chainweb?

So the question is: won't nodes bloat in disk space required? We get this question regularly, so we have material on it including in the whitepaper. First thing I'd mention is that there's a difference between a full node (1 chain) and full-full node (all chains) in Kadena. The decentralized authority that POW yields comes from the header stream + economics of chainweb, and has a disk footprint that's unlikely to be more than a single chains state db. Therefore, as a user, you can consume _just_ the header stream _and_ the chain(s) that your accounts are on w/o having to store the entire network. For a miner node operation/coordinator, you run and store the entire network. For a business, you run and store just the chains you're deployed to. So, as the network scales up to 1000 chains, and hits 5k-25k tps, users who want decentralized assurance won't need to store the entire network.

But there's no way around it, if you want to do 10k+ TPS you need to store 10k+ TPS. Anyone who says otherwise is either misleading or lying

At KDA, we just don't believe that it's rational to buy into the more anarchistic stance of the BTC community that a) the world economy can run on BTC and b) ever person should be able to store the ledger on their laptop... it's just not possible to do both at once

***

ETH, with it's nutty merklized state DB, has huge storage issues. . But for KDA, which didn't implement mainnet with a bloated DB in the name of a feature that no one ever uses. The merkelized state DB allows for merkle-proof-backed-queries, which no one ever bothers to use, vs our approach which just uses receipts, which is what pretty much everyone uses. It's a technical detail here, but I guess I get why the storage costs need to be hyper-expensive on EVM variants...

***

At the moment database sizes together are somewhere around 50GB. That's after 20 month of operation, about 12 month of which has been on 20 chains. At this point space growth is dominated by the number of blocks, which are produced at a constant rate of 20 per minute.

Tx throughput is increasingly adding to storage requirements. And we expect that eventually it will dominate. There are two ways how Kadena is going to address growing db sizes:

1. Physical per chain sharding. Each chain is already operating independently and using its own database internally. The only reason, why they are all bundled up in a single process is to make operation easier.
2. Shallow history for nodes. The validation logic only depends on the most recent history. Therefore consensus nodes (mining nodes and other validating nodes) don't need all of the transaction history. The fact that currently all nodes store the full history is an implementation choice and not an algorithmic or protocol requirement. Even with shallow history, nodes would still have to store the full pact state db for each chain. But those dbs are small in comparison (currently about 500MB on average) and per chain sharding allows to distribute the pact dbs to different machines. Overall, I estimate that with shallow history less than 25% of the current storage would be required which could be distributed to 20 different machines. At this point each machine would have to store between 500MB and 1GB of data.

Implementation of shallow dbs is medium priority at this point. I think, a total db size of < 100GB is probably fine. At this point networking and db-synchronization performance have higher priority. But, we'll implement it in time.

***

if some project claims to process 10K TPS, I'd like to know what storage system is used to persist those transactions. If each transaction requires just 32 bytes of storage --one SHA256 hash, which can't be compressed--, that would be about 25GB of storage per day. In practice it's probably 10 times more. How and where would that be stored? What indexes are needed for querying txs during validation? How often is each tx replicated on storage? Would it still be replicated often enough to be considered decentralized? Someone claiming to be able to handle that tx throughput would have to answer those questions.
