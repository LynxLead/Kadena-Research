# Best of Whitepaper

Traditional Proof-of-Work (PoW) as demonstrated in the Bitcoin network is a masterstroke of design that created the first truly trustless public network. However, PoW has critical limitations that curtail its potential to empower a truly massive distributed economy andis justly criticized for its slowness, consumption of large amounts of energy, and congestion pricing in the form of high transaction fees. Existing PoW networks are uniformly characterized by very low throughput, and while improvements through protocol modifi-cations have been made, none have provided a practical path to approach the throughput levels of modern fiat-currency payment networks1. Moreover, efforts that seek to replace PoW with new consensus models like Proof-of-Stake (PoS) or integrate the protocol with off-chain networks and processes (payment channels, side chains) degrade the assurance, censorship resistance, and trustless nature of the original PoW design. To resolve these current limitations of PoW we present Chainweb

### Regulations and PoS

regulations will easily apply to any staking design that designates distinct parties who participate in the deterministic confirmation of a given transaction. possible solution creates a PoS safe harbor like those found elsewhere but would damage the egalitarian blockchain ethos by requiring a central authority to ”erase” transactions. We maintain that staking designs put validators at risk of being subject to money transmitter regulation and enforcement as their unique identity and funds are essential to the effectuation of transfers in the system

permissioned architectures have scaling problems, and the MTA regulatory issues of PoS are still present should one actor validate a transaction on behalf of others. A PoW approach may be slower than protocols that use trust-based deterministic consensus, but PoW has no effective limit on the number of participants, while closed architectures face unavoidable performance problems as the number of consensus nodes increase.

### Security

The protocol itself does not impose an upper bound on network size, and is instead constrained theoretically by existing global IP infrastructure and bandwidth

A scaled Chainweb network can run thousands of chains simultaneously, increasing throughput to satisfy the requirements of modern electronic financial payment systems.\
Chainweb also serves to mitigate the worrisome energy footprint of current mining operations by distributing competition across many chains and reducing spurious competitive mining. Chainweb makes significantly more efficient use of hashrate than a single-chain PoW design.

The cross-referencing of Merkle roots serves to increase hostile-fork resistance as a function of the number of roots referenced. To replace a given block, an attacker must fork all chains that directly or indirectly reference that block beginning at the point that the reference occurs. Once full coverage is reached (i.e. every chain in the web references a block directly or indirectly) the attacker must fork every chain in the network. Effectively, the hashrate of the network is the sum of the hashrate of each peer, the combined power of which an attacker must overwhelm in order to guarantee acceptance of a fraudulent fork. The protocol itself consists of three elements: generation of probabilistic assurance, determining required peer references, and validating peer references.

### Bandwith

Block streams, for which there is an individual stream per chain, consist of the header and block for a given chain. The latter consumes the vast majority of bandwidth, but fortunately only operators replicating the entire network need to consume all of the blockstreams, who will already be running a large cluster to perform the replication, as the full base graphs will be infeasible to operate on a single server.

Meanwhile, the full Chainweb header stream is lightweight and fully captures the assurance of the full network. As such, it is possible for an individual to trustlessly operate a single chain in the network by accessing just its block stream along with the header stream.

While it is infeasible for most individuals to maintain a full network replica of networkswith large base graphs, it is also unnecessary. The security provided by the header streamis enough to assure an individual that their single-chain replication is correct

### Blocktime

We estimate that 30-second block times are feasible, and 15- and even 5-second block times may be possible as well

Given that production Chainweb implementations will likely favor diameter-4 or -5 base graphs, 30-, 15- and 5-second block times would represent average confirmation latencies of 120-150 seconds, 60-75 seconds, and 20-25 seconds respectively, while supporting network throughput of over 10,000 transactions per second. Under load and assuming that 5 second block times are feasible, a Chainweb network could achieve a lower practical latency (e.g. the time from 100,000 transactions between Alice and Bob entering the memory pool to each being confirmed) than any network using known deterministic consensus mechanisms

### Conclusion

In conclusion, Chainweb provides significant advances over existing approaches in scalable public blockchain. It provides unparalleled increases in PoW throughput while keeping the global hash rate, and thus energy required, constant. The confirmation latency of Chainweb is also significantly decreased from traditional PoW and is potentially even lower than that of PoS systems. Chainweb achieves these advances while maintaining the core trustless, decentralized nature of PoW. This protocol enables greater practical decentralization and enables the creation of an ecosystem where enterprises, individual users, and large mining pools can co-exist peacefully by acting selfishly. Chainweb avoids liquidity and centralization problems associated with using staked channels for scaling while also staying in the existing global regulatory context. We present in Chainweb as a solution by which PoW can be scaled such that it supports true decentralized economy.
