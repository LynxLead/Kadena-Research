# Sharding

With KDA, load balancing across shards is left to the users because they are the ones that ultimately pay the literal cost of balancing poorly (e.g. if everyone uses chain 0 for everything and it gets congested, the gas costs go up on that chain). But the node operators/miners/shards themselves have no control of how balancing happens in practice. Much like a transaction for ETH isn't valid on ETC, a transaction for KDA-Shard0 isn't valid for KDA-Shard1

***

no worries, it's a good question. If nodes have a say in which shards do work (vs in our model where it's devs/users who pick what chain to deploy to/keep a wallet on) then nodes have an incentive to give other shards work while they freeload. If I'm remembering correctly, Harmony has this problem at the moment, however I'm hesitant to say that ANY protocol that lets nodes "load balance" shards directly is decentralized at all (vs something like hashgraph/solana/elrond which is "decentralized" like EOS is decentralized.)

For Kadena, the aspect of the platform that balances loads between chains is gas fees/prices. For example, as of this week a total of 7M USD in gas fees have been wasted on ETH and it costs \~$10 to make a gnosis multisig wallet in gas fees. Let's say that instead of 1 crowded chain, like eth, we had a platform that had 1 crowded chain (thus high gas prices) and 19 vacant chains (thus low gas prices) in a single network... users and dapps would naturally migrate from the high-gas chain to the low-gas chains. Therefore, load balancing across shards is affected in KDA by the rational economic desire to tend to use chains/shards with lower gas fees.

Moreover, dapp devs can loadbalance contracts on KDA as well. A popular dapp like cryptokitties can be first deployed to shard 0 and, when it becomes really popular (though likely sometime before) it can be upgrade/expanded to also be deployed on shards 1-19 as well. So not only does KDA scale layer 1, it scales dapps too

***

## Problems with Sharding

***

I wouldn't say anyone agrees what "POS Sharding" is yet. The ETH2.0 people have some magic fairy dust idea, the Cosmos people are grounded in reality that sharding+POS doesn't work so they got for a Hub-Spoke model (layer-1 single chain, layer 2 spokes), and every other project falls somewhere in between. I have zero idea how POS's security doesn't degrade as a POS attempts to scale up. POS already has massive security problems that sharding exacerbates dramatically

With POW, the _work_ done is pinned to an external reality (hash difficulty) which makes it quick for anyone to verify (rehash+count the zeros). With POS, the "proof" is pinned to an internal reality aka _the stake_.

Regardless, all sharded POS networks basically degrade to one of two models in practice: high-centralization w/ supernodes (ZIL/hashgraph) or hub-and-spoke.

POW doesn't have this issue bceause POW is pinned to the external world (you can validate a header's POW w/o having to download the chain) + POW is stochastic, which allows for a seemless production of blocks in parallel

***

I'm not even really sure what other pure layer 1 scaling solutions are tractable:

* POS + chainweb-like sharding magnifies the security problems that are inherent to POS, and this magnification increase as the number of shards/chains increases (smaller stakes/fewer stakers on a per-newblock-per-shard basis). Near is probably doing the best to attempt to solve this problem, and yet I'm pretty sure it's not a solvable problem. Chainweb sharding _requires_ POW to function.
* All DAGs I've seen (solana, zil, hashgraph) are 1-time performance buffs the diminish in performance as adoption/usage increases (ie they get slower the more people use them). To my knowledge, chainweb is unique in allowing arbitrary post-launch scaling.
* everything else is layer 2 scaling in my book (hub and spoke, parachains, state channels) and all layer 2 scaling solutions are compatible with any POW (and most POS) layer 1 protocols.

***

I mean, I've yet to talk to a single eng not in Eth2.0 that _thinks_ that the Eth2 design holds water... most of us, myself included, are just like _wtf are they smoking_. Fundamentally, scaling needs _something_ objective to point to. For KDA, POW is that "objective" bit... at the cost of the solution being low level and users needing to decide what chains to have accounts on + devs to decide what chains to scale apps to. Cosmos' objective bit is their hub, at the cost of it being a single low bandwidth blockchain... so scaling is in the spokes/layer-two and going cross-spoke needs to settle on the hub + devs need to deploy an entire blockchain spoke (albeit smaller and staked from the hub) to run an app. Lightning's objective bit is BTC, at the cost of being solely layer-2. Hashgraph's objective bit is _centralized super nodes_, which comes with the cost of _centralized supernodes_.

***

If shards can "send work" from one shard to another, it's near impossible for the shards to be "equals" as it injects a massive new economic incentive system at the validator level -- one example off the top of my head is that validators can now collude to arbitrage failures in the gas model. Better for users and dapp devs to pick which chains to run on, as the congestion fee costs are covered by the consumer in a very transparent way.

***

extra https://twitter.com/EdgarArout/status/1279593449654644736
