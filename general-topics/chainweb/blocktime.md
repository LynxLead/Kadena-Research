# Blocktime

POW settlement time is lightning compared to what came before (remember that in finance a tx and settlement arent the same). We're talking about a fully reliable settlement time on the order of minutes with KDA. That's crazy fast. IMHO "fast finality" is a solution looking for a problem... because you can use state channels or layer-2 to achieve it. Layer one doesn't need sub-second finality, it needs scale and robustness.

every time we scale KDA, we reduce blocktime. It's a block every 30s per chain, so right now KDA has a 3sec block time

when we got to 20-chains, that drops to 1.5 sec per block

So yes, if a given layer-1 can scale it requires a _tractable path_ to having super-small blocktimes (e.g. a 1000 chain KDA would have a blocktime crossnetwork of 0.03 sec). This is why we talk about "blocks produced" so much -- it's a really clear _this thing is different, it scales_ metric

***

Currently, with 10-chains, the block time across the entire network is \~3 seconds. 1 block per chain per 30 seconds. With 20 chains, that drops to 1.5 sec-per-block **while simultaneously** the capacity of the network is doubled. At 100 chains, that blocktime drops to .3 seconds per block. This is something fundamental to notice: the current version of KDA is as slow as it will ever get vs all POS competitors that launch at their top speed and slow down as they scale/get adopted

***

Uhh, kadena has a faster blocktime than _most_ POS chains and all POW chains. Kadena has 30sec blocktimes per chain, but there are 20 chains \[currently] running in parallel, so the network blocktime is 1.5sec. Last I checked only tether's blockchain and EOS have faster blocktimes, but it's been a while since I checked. once we scale to, say, 50 chains, the blocktime will drop to sub-second blocktimes

***

So there's a couple times running around in your comment. One is "confirmation time" (aka confirmation block depth), which in KDA is \~2min and in Eth is \~5min, but is always a "recommended" class of measure. It's a bit unknown what confirmation time "means" in practice for a dapp as many/most don't wait this long between transactions. However, we're really talking about the wrong thing here -- public blockchains are settlement layers, which needs throughput, and not transaction layers, which is what a L2 is for _if you need real transaction performance_. Real tx perf is sub-second latency, if not sub millisecond, which a public blockchain can't do ever. Best you can get is collecting txs into some other faster but more centralized ledger -or- some zk kernel and settling it to mainnet periodically. Moreover, its rare that an app needs sub-minute transactional latency and not sub-second. However, it's _common_ if not universal that an app needs more throughput and can leverage horizontal scaling, which is where the parallel chain design of kadena comes in. tl;dr -- a dapp running on one chain gets 1 block per 30sec to work with, but a dapp that's scaled across the network gets 20 blocks per 30sec to work with. Postnote: Gas costs, not tx latency, is the major blocker to dapp adoption of the two.

***

the 30sec determination is made by balancing "block validation time" and "block propagation time" with the reality of the current infrastructure (eg dedicated fiber lines would imply network latency got lower) and how much work we want to do in a block (tx processing takes time and shouldn't be more than a small percentage of the work that goes into block construction) and orphan rates (ETH has uncles, so orphans are still useful for security even if the tx get rolled back). If we lower the block time, holding all else equal, orphan rates will increase and we'd have to lower the per block gas limit

***

IMO crypto is about settlements not trading. 30sec latency for settlements globally is lightning. If you want something faster, people should build layer-2 approaches that have hyper-low latency at the cost of some centralization. I don't mean a lot of centralization here, just the amount of centralization that naturally occurs with any POS chain.
