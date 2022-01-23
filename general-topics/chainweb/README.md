# Chainweb

As an engineer I see a block chain as a distributed database system with untrusted and adversarial users. The goal is to scale throughput with low latencies and fast convergence (consensus/security) under the assumption that 51% of all users follow the rules. That is a relatively simple and well understood model. Usually, you don't have to make assumptions about block chain features and Crypto markets in order to argue that an algorithm for it is correct. Just state of the art computer science and mathematics is enough.

The elegance of Nakamoto Consensus is that it provides a solution within the realm of this simple model. But Bitcoin has reached its scalability limits. Many solutions, in particular POS and layer 2 approaches, try to achieve scalability by moving to much more complex models. It is much, much harder to reason about those more complex systems. In particular, there are often non-trivial trade-offs between performance and security and consistency of consensus, which require strong domain specific assumptions as justification. Chainweb in turn improves upon Nakamoto Consensus by using results from computer science and mathematic. Those results are studied and applied in a much wider field than just block chains.

In short: Chainweb inherits the elegance of Nakamoto Consensus. It's simple. Its scaling solution is based just on concepts from computer science and mathematics.

***

In a nutshell: In a single chain system mining-nodes are racing against each other, producing orphans in case of conflict. In chainweb mining nodes concurrently extend the chainweb by distributing hash power across chains. This greatly reduces the number of orphans, which allows reduced the block time, reduce latencies, and increased tx throughput. If the chains were independent this would come at the cost of reduced security. In chainweb, however, the braiding structure of the chains guarantees that the Merkle hash of a block includes the hashes of the blocks on all chains at the confirmation depth. Thus, at confirmation depth (actually much earlier, with ten chains at depth 2) the security guarantees are the same as for a single chain.

***

In Ethereum uncles are orphaned blocks that are incentives by the protocol. That's Ethereum's way to achieve low block times, which result in higher orphan rates, while keeping the chain secure. However, while uncles help with security, they reduce for throughput, since all tx on them are lost and must be re-introduced.

Also, our block times per chain are still a bit more than 2x slower than Ethereum (so we can get away without uncles or similar on a single chain). Chainweb's throughput is really a function of the number of chains.

In a certain way ghost and chainweb attack layer-1 scaling with a similar approach: instead of having miners race against each other on every single block, let them work in parallel on blocks within a certain sliding time window and combine the weight of the overall work. So parallel work isn't wasted.

However, in my opinion the approach from chainweb is much simpler. Ghost looks more like patching the already existing protocol. Chainweb is more principled solution to the problem. And, yes, and the chainweb algorithm scales infinitely.

***

In the design of chainweb we always have scaling in mind. The overall architecture and the algorithms support running nodes in data centers and using state of the art technology for operating larger services. For instance, it will be straight forward run per-chain pact services on separate VMs in cloud clusters and let mining-coordinators and consensus nodes use these through load balancers. It would also be possible to parallelize cut processing within consensus nodes. Further, the data schemes support per chain sharding and are designed such that chain data can be persisted on remote storage backends with efficient and small in memory caches.

However, at this point the resource footprint for chainweb nodes is so small that all of this would be overkill. Instead we try to make it simple and cheap for people to run complete nodes which include just a single instance of each component (pact, mempool, mining-coordination, and consensus).

But we are prepared to provide the features for running nodes at data center scale, once it becomes necessary.

***

Miners don't have to mine all chains, but they definitely must mine more than a single chain to be efficient. I theory it's enough if each miner mines a sufficiently large subset of the chains and those sets overlap between miners. In practice each miner mines all chains. Chainweb is designed in a way that a miner can mine all chains on a relatively limited set of resources. It's relatively cheap to shift between chains.

***

Understanding why Chainweb is more efficient than mining a single monolithic chain is less about block chains and more about the theory of concurrent and distributed computations.

A single chain is a sequential computation. A block corresponds to a single computation step which results in a new state. A block chain is a distributed system and all miners (processors) compute the next state in parallel. On a single chain with just one block per step that means that each miner (processor) races against all others. That's wasting resources.

In chainweb a global computation step is split into many blocks, which together result in a new distributed global state, which we call a cut. Cuts can be computed by miners in parallel which avoids wasting of resources.

Since miners are adversarial there is still some racing, but it's much less. In a system with 10 chains there are usually 3-5 chains that are unblocked and available for mining. When miners choose randomly they are distributing the hash power evenly across those 3-5 chains.

This explains why chainweb is more efficient than a single monolithic chain. The key for understanding that this is done without sacrificing security is to understand the properties of the graphs that are used to braid a Chainweb.

Chainweb graphs have a very low degree and at the same time low diameter, which means that they have a very good expansion. That means, that while each node has only a small number of neighbors, each node of the graph depends on all other parts of the graph in just a very small number of steps. In practice that means that each block on every chain depends on all blocks on all chains at just a small depth in the history. Even with a 1000 chains that depth would still be smaller than the the usual confirmation depth of a single-chain block chain system, like bitcoin or ethereum.

In other words, the efficiency gains due to concurrency in Chainweb come for free, since the additional waiting time for blocks to collect enough weight (hash power) is subsumed by the usual confirmation time.

***

It's bad if you scale out without demand for the extra capacity, because you'll still have to pay for the infrastructure. In particular, since with Chainweb you can't scale back in again. When you run a normal service on a cloud stack you can scale in and out relatively quickly based on demand. Chainweb can only scale out. Once a chain is producing blocks you can stop it. Well, I guess the overall block rate could be lowered to compensate for decreasing demand on a larger number of chains. Still it would require a fork and is a slow process. If Chainweb had started right away with 1000 chains, each node would have to run 1000 chain databases and 1000 Pact processing instances, and process new 2000 blocks per minute. A lower block rate would increases per chain latencies, so it's not a good solution.

That's also the reason why we only increase to 20 chains it this point. It proves that the technology exists and the system is ready to scale as needed -- without adding too much extra operational costs. At this point Chainweb has tons of spare capacity even on 10 chains

***

The basic consensus algorithms behind PoS have been around for a long time. They are usually complex and rely on many assumptions in order to scale. I think that's the reason why the Bitcoin founders didn't use them but instead developed Nakamoto consensus (PoW), which is decentralized, simple, and elegant.

The problem with the original Nakamoto consensus is that it didn't scale beyond some hard limit. To meet modern TPS demands, people just went back to those classic distributed consensus algorithms or layer-2 solutions, ignoring all the reasons why Bitcoin didn't use those in the first place. But it was the easiest thing to do.

Kadena, instead, figured out how to scale Nakamoto consensus. So it inherits all the benefits of Nakamoto consensus and, in addition, scales. In my opinion, Chainweb can claim to be in the tradition of Bitcoin, while PoS systems can't easily make that claim.

***

Overall, chainweb-node has very low resource requirements.

* 2 CPU cores
* 4 GB of RAM
* 30 GB SSD disk (including the operating system)

Currently, disk space growths mostly linear with block height, since tx loads are low and many blocks are empty. Once there are more txs per block, disk requirements will grow. Would be interesting how it performs on spinning disk raid system.

Currently we have lots of headroom for performance. If we should hit bottlenecks regarding in any of CPU, RAM, disk, or Networking, the solution would be to distribute tx processing for chains on physical shards.

At this point the system is logically shared: each chain runs it's own Pact instance, mempool, and sqlite database. Those could be moved to different OS . processes or even different physical machines.

The reason why everything runs in a single chainweb-node binary now, is that resource requirements are so low that it works just fine in a single process. And a single process is much simpler to run and administer.

***

Overall the hash power is used more efficiently in Chainweb than in a single chain system, since there are always many chains mineable. So miners work concurrently on different blocks without wasting hash power on orphans.

The low orphan rates at short block times are key for the performance of Chainweb's consensus. Single chain systems either have to use large block times (Bitcoin) or accept high orphan rates (Ethereum/GHOST, uncles blocks are wasted hash power, since they don't contribute the tx payload).
