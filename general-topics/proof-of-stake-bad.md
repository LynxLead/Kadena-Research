# Proof of Stake bad

The idea of "**Kadena figured out how to scale POW... and thus solved the biggest problem in crypto since the inception of BTC**" _Has trouble getting mindshare because lol VC's love POS because it's neuvo-feudalism_ Whoever is a land owner early gets to be a land owner forever... because they as a class can refuse to sell the land

\---

Ethereum moving away from PoW to PoS for scalability is creating a dangerous precedent for cryptocurrencies. The go-to consensus mechanism for creating new blockchains seems to be some form of PoS which trades off decentralization and security for scalability. Proof-of-stake requires validators always to be online as they can’t miss any calls. The entire protocol’s trust comes from this high level of interactivity. We have already seen slashing issues erupt in PoS networks where an outage leads to blameless operators being punished. If there was a massive power outage, PoW systems could return to normal in no time, not the case with PoS systems.

The crux of PoS is that it utilizes a system that allows for the free exchange of money, AKA crypto itself, with no regulation. Therefore, it bears upon economics and will. The moment a sufficiently motivated crypto whale, not someone lower like a crypto minnow, determines that they want to attack a PoS network, it’s just a matter of spending money. PoS does not have a structure in place that impedes others from coming into the system. PoW has been battle-tested to incentivize ethical behavior while making it challenging to be a bad actor. Currently, with all the new entrants to crypto, money is easy to make. When that changes, attacking PoS will become lucrative.

##

Staking and POS is very good for large VCs that want to control what supposed to be a decentralized system... honestly POS degrades into feudalism longterm. We're not a fan. Moreover, POW is fundamental to sharding that works... I don't know how to make POS + chainweb function despite trying for 2+ years. Much like Visa, POS is good for a low throughput, near-instant centralized single chain/settlement layer. POW is good for a high throughput, pretty-fast large decentralized network of chains/settlement layer.

in practice POS, it's closer to feudalism. Whoever is a land owner early gets to be a land owner forever... because they as a class can refuse to sell the land

***

> why is that "Monumental Advancement" not translating and making noise in the mainstream?

re:"why not yet..." -- this ones easier to address: the culture in crypto is kinda crap. There's 5+ years of nonsense to deprogram, specifically _POS is the only future_ and we're up against a lot of influencers and "thought leaders" that have large vested interests in POS being the only future (despite KDA being evidence to the contrary). So it's gonna take time, because most of the biggest names have a lot to lose by even crediting KDA with shipping sharding.

***

For POS, you're supposed to stake, long term, all the time. you can't just hodl. This sounds great, _now your tokens can earn you a return_, but the long term impact is a **strong** incentive to centralize, be that on an exchange (how stakes for you and allows you to day-trade) or into one of the few strongest POS validator providers.

So, if you have a lot of tokens :cough: big vcs :cough: you build a validator that's top-tier and get people to use it (for a fee). Long term, the big VC increases their already dominant token position. As for exchanges, they become _major_ players in the health of the protocol. That said, from what we've seen so far, when a POS system has a hiccup/failure and slashing's supposed to happen, the "decentralized protocol" 's devs/founders quickly rewrite the ledger...

tl;dr -- it's too soon to say _how_ POS token economies function, just that they are very different from POW.

The weird bit, which I can't really describe succinctly, is how much a POS system looks like a _decentralized_ Ponzi or MLM. This is mostly because the only way to buy/get tokens is to buy them from people that already bought them vs POW where anyone can mine and capture newly issued tokens (and in equities where a company can sell new stock). It's a loose metaphor that I'm not sure I could convince a regulator of, and yet a defining feature of MLM/Ponzi/POS is that inventory can only be purchased from previous owners.

***

PoS has several problems. The biggest are that it's a pay-to-play reputation engine which favors the richest stakers. The others being that sybil attacks are a hard problem, and they lack a decentralized and cryptographically strong method of existence proof in the chain and doing cross-system transfers. PoW has the last in the form of Simple Payment Verification (SPV)

"re:Why not PoS btw?" for the reasons @𝓔 m i l y mentioned plus another big one -- I don't believe that true layer one scaling is possible w/o an objective work function. A multi-chain (chainweb) arch doesn't work for POS because the validation of a peer chain is subjective to the state of the peer chain. This implies that all replicators must replicate all chains as the security isn't captured by the headers alone. It's a subtle point but an important one -- because POW is objective, the decentralized security found by replicating one chain + the header stream for the network is the same as replicating the whole network. This isn't to say that someone wont try to apply POS to chainweb, just that it will be very fragile without augmentation because the bribery issue and nothing at stake problems get _magnified_ as chain-count increases. One solution to this to have one chain where everyone stakes to, and use those positions to determine validators for peer chains. If you iterate through that solution idea, you end up at hub-and-spoke ala cosmos, which has the liquidity problem that comes with all layer-2 solutions (you have to de-stake from one peer/spoke, settle to hub, then re-stake to new spoke, to transmit funds... and the hub is low bandwidth so that de-stake is expensive). The other solution is to have the multiplexing of executions take place post consensus, which is effectively Hashgraph or Solana. These approaches have the fundamental issue in that, Ahmdal's Law + small world problem basically limit the overall parallelized network throughput to 6x sequential (10x max).

tl;dr -- it's not a "Why not PoS" thing so much as a "I can't believe you can scale PoW" thing

I've been working on _is it possible to use chainweb w/ anything but POW_ problem for years, talking with the top people in the space on the question, and the best I can offer is _maybe it could work with proof-of-space_

***

Now that doesn't work with POS in practice, as the main validators are rarely if ever actually anonymous... I think the industry will be surprised what happens when some major stakers receive a national security letter and a gag order demanding that accounts XYZ be banned

***

and as you know, POW is unbounded in node count so there is zero impact on performance as nodes are added

VS all deterministic BFTs whose performance degrades with consensus node count (this is a fundamental aspect of dbft and thus all "fast finality" POS"). I highly doubt we'll _ever_ see a +200 node POS network with high utilization... because I can get kadena kuro to maintain consensus with 5k+ nodes but **not** executed transactions at anywhere near the same throughput. POW being probabilistic consensus is a **feature** that allows for globe spanning trustlessness.

***

Another aspect: POW with Nakamoto consensus is a relatively simple system with clear economic incentives which makes it a fair game. Its relatively obvious that in order to win the game it doesn't make much sense to try to explore obscure aspects of a complex protocol and market. Instead the best strategy is straight forward investment in innovative hardware and energy sources. That drives innovation and jobs in a "real" economy.

To me POS looks much more like a system of mere entitlements without connection to real world economic productivity.

***

With PoS there is no way to force stakers to give up control over the network. If the early holders decide to keep 51%, they can do so.

With PoW everybody can just start mining. It's an investment and it may include buying or even building hardware. Yet, (assuming that a sufficiently large portion of new coins is created via mining) nobody can simply keep 51% control without continuously investing in mining.

***

POS is decentralization within a closed group of stakeholders who's share and control increases over time. POW is truly openly decentralized. It's impossible to maintain control in a POW but just holding. One has to continuously invest in mining in order to maintain control. So, POS system have a builtin tendency to centralize control over time. POW has a builtin tendency to decentralize over time.

***

\###PoW/PoS Hybrid pos/pow (like dcred) is a PR mask over a POW system. Yes there's POS in there too, but if the POW and POS sides of the beast, the POW side wins. All POW participants are POS stakers, the inverse isn't true, so they have ultimate control if they all agree to fork. It'd probably kill the network, but that projects more about testing if hybrid can get along with itself and having a token, plus some extra throughput, vs a bigger concept. in effect, it's small enough that there's not enough money on the line for the fragility of the hybrid POS/POW ceasefire to become apparent.

***

\###Cosmos

hub-and-spoke ala cosmos, which has the liquidity problem that comes with all layer-2 solutions (you have to de-stake from one peer/spoke, settle to hub, then re-stake to new spoke, to transmit funds... and the hub is low bandwidth so that de-stake is expensive).

\###Hash + Solana

The other solution is to have the multiplexing of executions take place post consensus, which is effectively Hashgraph or Solana. These approaches have the fundamental issue in that, Ahmdal's Law + small world problem basically limit the overall parallelized network throughput to 6x sequential (10x max).

***

\
\
