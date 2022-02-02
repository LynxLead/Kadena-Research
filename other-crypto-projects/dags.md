# DAGs

DAGs have the fatal flaw of the "small world" problem in that a killer dapp actually constricts the overall network performance. It's why a DAG's should come with a warning label that posts both their "Best-Case Performance" AND "Worst-Case Performance" numbers. This is why DAGs are not used for scaling in HFT/finance, even though the industry tried them out in the 90s... DAGs suck at scaling in production BUT they make for fantastic performance demos and POCs... which is why finance bothered to try them in the first place (this was in the era before the senior leadership at funds were tech/eng types and didn't know better)





re:DAGs -- all blockchains are DAGs, so the terms misleading. What we're really talking about is concurrent transaction execution (eg if two txs are causally unrelated, they can happen in parallel/any order) vs sequential (every tx must execute in an absolute order). As a trick for high performance demos, DAGs are great. I can make a blockchain+dag that demos 1M TPS with little effort. The problem is that DAG speedups are bounded by causality, so in the demo everything is unrelated to it can all run in parallel but in the real world you have the "small world" problem and Ahmdel's Law that cap a DAG's max performance boost at 5x-10x the speed of if you were just running a sequential strategy. If you're wondering why SOL is so congested, even though they said/demo-ed much higher numbers, this is why. In practice, I don't expect a "DAG chain" to exceed \~1k tps on real world workloads.

and, the problem with using DAGs to scale is that you get a one-time finite speedup. You can't 10x a DAG's performance by adding more DAG or anything.

If you want some intuition for this, dags have a "width" that is the max number of unrelated txs that can be executed in a given period. If a DAG is processing a bunch of p2p txs between accounts, then many of those txs are unrelated and the DAG can be wide. But if you have a killer app, say Uniswap, that many accounts interact with on a regular basis, then the DAG is much narrower because the various txs are all touching the same app and thus can only be processed one at a time.





Following on from SpecR w.r.t. scalability, DAGs have a large difference between upper and lower limit performance bounds. The reason for this is why you'll hear that DAGs have known scaling problems.  Here's an easy example: say you have a simple coin transfer tx between two accounts, your VM can do 10 of these tx/s per second, and the consensus overhead w.r.t. time is baked into the 10tx/s number.\
In a DAG, the performance of the network varies based on how it's used. The upper bound can be near infinite IFF different users are involved in every tx (eg: acct\_a -> b, c->d, e->f, etc) -- they can all happen in parallel globally because they are causally unrelated.\
\
However, the lower bound of a DAG is determined by the case where every tx is causally related (eg a->b, a->b, etc) and in this case is 10tx/s. This has a pretty good model for thinking about it\
([https://en.wikipedia.org/wiki/Amdahl%27s\_law](https://en.wikipedia.org/wiki/Amdahl's\_law) -- the sequential portion of a program bounds the max speed improvement).\
Thus, the problem is DAGs is that their scalability is dictated by how they are used -- they aren't "CryptoKitties Resistant" in that a cryptokitties-like app can and will congest the entire network.\
Even if you don't get a kitty, someone that you are interacting with probably has which means that you get caught in the cascading causaility web that killer-apps trigger.

Chainweb is different in that the parallelism it uses for scalability is upfront and static. How people use it doesn't impact overall performance, the exec envs are sandboxed. This means the upper and lower performance bounds are quite tight... but that the roadmap to higher scalability is clear. If the max speed of a single chain is 10tx/s, then the min and max throughput are both 10tx/s\*num\_chains
