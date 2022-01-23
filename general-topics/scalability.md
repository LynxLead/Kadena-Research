# Scalability

No one should forget that a general solution to layer 1 scaling as been **the single largest unanswered question in crypto for the last 10 years**. When critics call BS on crypto, a very common refrain is "5-10 transactions a second will never do it". A lot of people have had a lot of ideas for how to solve it, and to my knowledge KDA is the only one that actually worked. Invalidating the "trilemma" takes some doing.

***

> Chainlink has created incredible returns by focusing on solving an essential problem that the entire space needs on which no one else was working.

The biggest unsolved problem in crypto for the last decade has been: how do we scale layer-1? Specifically, how do you shard/partition layer-1 ledger state. It has been an unsolved problem for so long, and so many BS "solutions" have been pitched, that most people have given up on decentralized layer-1 scaling being a solvable problem (and have turned to centralized and/or layer-2 solutions instead. So yes, KDA didn't focus on a problem that "no one else was working on" like Chainlink was and instead they focused on a historically impossible to solve problem that everyone agreed was **the big problem to solve**... and managed to actually ship the solution into production.

***

also, the trilemma a) was made up to mimic the CAP theorem (but mostly as an excuse for why vitalik is bad a shipping updates) b) was always BS c) never talked about disk space requirements d) requires a feasible solution not one in practice. Crypto is too centralized already and POS makes it 10x worse. What we need is a solution that can be decentralized and the economic incentive (adoption at scale ) for various parties to compete directly thus making it decentralized in practice.

***

Kadena is a literal representation of the peak of a lot of what the top minds of crypto think is the future.

You'll never scale a POS w/ only layer 1 (and yes, this means that Eth2.0 will never launch, it'll get a rebrand and new design direction) on-chain governance doesn't actually matter because humans ultimately control the software they run so they can vote with what they install. Thus it overcomplicates how POW works eg miners vote with their hashrate.

***

horizontal scaling means you can run a monster network that spans data centers if you wanted to. To be extreme, imagine BTC with a block-size of 1TB... it wouldn't work. The bandwidth requirements alone would be insane, and that server would be a monster. But a kadena chainweb of 1M 1MB-per-block chains would work and could be colocated in multiple data centers with individual servers replicating subsets of the overall network. horizontal scaling is always the only solution to scaling. Everything else has a speed limited horizontal scaling, when done right, is unbounded

***

But the idea that one can have a single global ledger that is a) decentralized and b) that supports, worst case, more than maybe a few thousand txs a sec is just nonsense. Either one needs to shard the ledger, like KDA, or one needs to centralize. We're not in some alt universe where this is possible, despite the +$100MM invested in projects that claim otherwise.

***

Remember that unlike BTC, Kadena can always scale up with hashrate to provide more throughput (more chains). BTC at this point is ridiculously over-secured, and it is a waste.

If BTC could actually scale, the electricity use could be well-justified. If you could plan on BTC always taking 1 hour to confirm a tx, no matter how much traffic, we could be clearing the entire stock market on BTC, and it would outperform the current system, as 1 hour is way faster than 3 days (the current T+3 clearing in stocks). But ... it can't scale. Kadena can.

***

The bottom line here is that scaling to the point where you can use a layer-1 blockchain to buy coffee will require massive infrastructure. There's simply no way around it. You're not going to be able to run a node on your phone that handles all the transactions in the U.S (at least not given the current capabilities of phones). And it's not just the disk space. All this stuff also requires significant bandwidth and computing power.

Kadena engineers have worked at large companies like JP Morgan, Microsoft, Google, Disney, etc. We understand what kind of work is involved in building systems of this scale, and we have kept many of those considerations in mind as we've developed the system we currently have.

***

I always wonder why so few people talk about db sizes and everybody just throws out those tps numbers.

The keys to scalability for a crypto project are:

1. An algorithm/protocol that supports massive horizontal scaling and sharding of payload databases (while providing efficient consensus) and
2. Industrial state of the art cloud engineering.

Most blockchain projects lack both. To the best of my knowledge Kadena is the only PoW block chain that solves the first point at the base layer.

The second point is, in theory, straight forward, since the problem is well understood and there are established best practices and solutions. However, in todays competitive hiring environment it is very hard for a small company to find and hire experts who have experience with scaling really large systems.

For Kadena, as for many tech startups, I think, the largest challenges are in the second point. For that reason, the whole system is designed from ground up with scalability and sharding in mind. At this point chainweb-node is a single binary only to help with the second point and make deployment and operation easier. As soon as a single process does not scale any more we can easily split it up and distribute the Pact processes and databases for each chain to different processes or even machines.

Once chainweb-node is physically distributed, the challenge will be to deploy and operate nodes as distributed cloud services. At that point it would become difficult for a private person to run a full chainweb-node, but instead it would require cloud infrastructure and a dedicated devops team. We'll be getting there

***

Anybody developing systems that process transactions at this scale should invest in basic distributed systems expertise and should look into ways to shard their data.

One can not expect that a system that can process 500-1000 TPS is for free. Even a centralized system would already require a substantial amount of resources. A fully decentralized system needs even more.

***

if some project claims to process 10K TPS, I'd like to know what storage system is used to persist those transactions. If each transaction requires just 32 bytes of storage --one SHA256 hash, which can't be compressed--, that would be about 25GB of storage per day. In practice it's probably 10 times more. How and where would that be stored? What indexes are needed for querying txs during validation? How often is each tx replicated on storage? Would it still be replicated often enough to be considered decentralized? Someone claiming to be able to handle that tx throughput would have to answer those questions.
