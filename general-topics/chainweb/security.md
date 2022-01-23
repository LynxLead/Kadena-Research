# Security



> performing a 51% attack on a single chain takes 2.55%.

This is only true when attacking the most recent block. But, usually, that's not called an attack -- it's called mining

Doing a 51% attack on requires to reproduce history up to the common confirmation depth. For chainweb, doing an attack at the very moderate depth of 4 (on average 2 minutes), already requires overcoming all honest hash power on all chains.

Do to the probabilistic nature of Nakamoto consensus, 51% attacks usually can be done with less hash power than 51% by exploiting the inherent variance in the mining process, by trading waiting time for hash power. Essentially, one just does many attempts until one is lucky. This strategy becomes more difficult as more blocks are involved in the attack. For single chains, there's one block per additional confirmation depth count. In chainweb there are 20 per confirmation depth count. Thus, this strategy doesn't work as well on chainweb and 51% percent attacks (beyond a depth of 3) are much harder on chainweb than on single chains.

So, on chainweb, even for moderate depths, the actual hash power that is required for 51% attacks is very close to 51%, even when having the malicious hash power available for long time and doing many attempts.

***

Another, aspect that increases the security of chainwebs braiding in comparison to single chains, are lower orphan rates. On can assume that a malicious 51% fork won't produce orphan. So the fork only needs to overcome the hash power of the honest network minus the hash power spent on orphans.

"Classical" chains, like Bitcoin, solves that problem by using very long block times and limiting the throughput, thus making sure that miners have enough time to sync in between blocks. But that's inefficient.

Ethereum addressed that problem by adopting Ghost, i.e. by using orphan blocks as Uncles. This allows Ethereum to run at block times of about 15 seconds. However, Ghosts incentives mining of orphans (up to some depth), which reduces the risk of 51% attacks, but don't contribute to the transaction throughput of the chain -- so it's inefficient, too. In chainweb miners work concurrently on the next block height, which reduces races and thus orphans. Chainweb currently has about 2.5% orphans on average (as observed on non-mining nodes, mining pool probably see somewhat higher values), while producing a block every 1.5 seconds (on average).

***

By loosing 50 hash power, the network would slow down and an attack would take much longer. This makes it more costly, less likely to succeed, and gives other users more time to react.
