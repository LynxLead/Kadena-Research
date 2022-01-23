# Stuart Popejoy

> The real competitors are in enterprise, and we outlasted them (haha IBM suck it!!). One time IBM got us kicked out of a conference because they were the lead sponsor. It's actually illegal to do that. Not that we cared

> It's kind of wild, we're haskellers at kadena so we know what kind of caliber they have on their haskell team at Cardano. Yet we shipped Pact 1.0 in 2016 and they still haven't shipped Plutus?!? It makes no sense

> Public cryptocurrency has HUGE value to the corporate treasury space, but it's going to take careful footwork to get there.

Cosmos is not decentralized, it's proof-of-stake. Individual cosmos/tendermint chains decide how much decentralization they want.

I don't think anything is immune but we at least have standard APIs and things like TLS-authenticated hosts which increases the cost of DDOS for an attacker considerably. It's something Ethereum AND bitcoin have had in their roadmap for a long time.

Well, for one, all of them can't scale without losing decentralization. Take secretswap on Cosmos. It's fast, for now. But success will be it's enemy as it has a hard upper limit on transaction throughput.

I wouldn't be so sure Secret avoids frontrunning. Some of the most damaging frontrunning has nothing to do with mempools and everything to do with price oracles updating.

Scaling isn't a magic bullet either -- for any exchange to ultimately dominate, it can't run on just one platform. That means you have to solve (a) liquidity fragmentation across multiple venues and (b) a story for running the _same exchange_ on different platforms. Kadenaswap is the only exchange who's roadmap has it running on multiple Kadena chains, AND cosmos, AND polkadot.

***

In all seriousness, I'm worried about the reliance on illusory differences with POS from platform to platform making people think one is meaningfully distinct from another -- in ALL CASES it only takes a minimal amount of financial collusion to cause security issues. Meanwhile things like "proof of history" etc are academic nonsense.

***

Interop in DeFi means bridges on+off Ethereum, and decentralized is best. Yet Ethereum won't support "new" curves and hashes, like BLAKE and ED-25519, as built-in contracts. Eth core devs have blocked good-faith efforts since 2016. It's anti-competitive and pro-centralization.

At this point though it's patently anti-competitive and must be called out as such. It keeps assets trapped on Ethereum, covering for Eth's 2.0 botched rollout against new+proven blockchains like Kadena and embargoing decentralized interop from neutral competitors like ZCash.

***

#### altruism

There's a tension in crypto financial engineering playing out that concerns me, which is the layering of financial protocols to achieve security. All too often the main defense against plutocracy relies on game-theoric notions of "rational altruism". \1

Put another way, there's a widespread practice of securing protocols by making them "too big to fail" with the idea that rational altruism will supply the necessary coordination that will prevent the system from falling apart. \2

For instance, combining a POS network with a liquidity regime for an exchange or index that depends on the economic power of the token, implies that in a liquidity crisis, you could also have a security crisis. \3

It can seem like a no-brainer to layer them, why not? A platform token, POS or POW, is a natural fit for e.g. being the best pair on a #DEX with alts and stablecoins, due to the inherent liquidity and access available. This is how Kadenaswap drives value to $KDA for instance. \4

Notice that no complicated engineering or modeling is required for this. $KDA (or $ETH on Ethereum) can fill this important role without ever having to think about how that affects platform security. A priori, a POS coin is less independent of exchange dynamics. \5

But if DEX on POS is iffy, far sketchier is ramping up that coordination to supercharge liquidity for derivatives or indexes. A notion of altruism emerges, essentially asserting that it's not in whales' collective interest to attack the platform.

AKA, too big to fail. Who needs it? We already have megabanks :). Here's the thing: you don't have to go POS to scale! Scalable POW on lets financial innovation leverage the liquidity of KDA with no possibility of destabilizing the protocol.

***

Will and I started out in "enterprise blockchain", as a logical segue from our efforts at JP Morgan. The journey to today and our focus on scaling proof-of-work may seem like a U-turn but many of the guiding lights are unchanged. \1 @kadena\_io

First is the seemingly obvious fact that we owe all of this to Bitcoin, Nakamoto consensus, and Haber blockchains. Everything happening today -- smart contracts, DeFi, NFT -- has its roots in the Bitcoin design. \2

We launched with Pact, our smart contract language, and while it might seem to be on another planet from Bitcoin script, that is its true inspiration -- Turing incomplete, focused on safe custody, and reducing the surface area for attacks. \3

This has as much value to "enterprise" as to public blockchain. One day the trustless model will "click" for enterprise, and then smart contracts will deliver value. For now the action is indisputably in public -- where digital value is created, driven by smart contracts. \4

The other side is the awareness that scaling is everything, whether it's a blockchain, a stock exchange or a webstore. Scaling means using proven techniques, and any innovation is necessarily built on extremely solid foundations. Scaling never "starts from scratch." \5

For enterprise, this meant ensuring that consensus could scale to high node counts, like Kuro, maintaining 8000/s throughput with over 500 nodes. In comparison, Fabric or Corda can't handle more than 20. This is how our layer-2 configuration reaches 480k/s. \6

For public, this meant proof-of-work, Bitcoin-style, but scaled: by using techniques in the Satoshi paper, but also Adam Back's sidechains paper from 2014. Small improvements reap huge rewards in throughput while maintaining or improving the security of the original design. \7

It's important to remember that Bitcoin didn't innovate in it's component parts, but in how they worked together. At we're continually inspired by this model and it's how we're delivering the future of digital value.

***

### speed

Blockchain is best thought of as a settlement layer. If fast finality were so important neither BTC or ETH would have succeeded. kadena's scalability and security come from advantages offered by Nakamoto consensus/Proof of Work, with one in particular: non-interactivity. \1

Proof-of-Stake systems are highly interactive, with consensus requiring nodes to be "online". Indeed we have already seen slashing issues erupt in Polkadot and others where a network outage leads to blameless operators being punished. \2

PoS interactivity hurts trustless bridges: the validator-set stream must arrive in a timely fashion for authority to be transmitted. This is bad news for sharding: if it's this hard to validate one chain, imagine 10s or 100s like Eth 2.0 promises, and kadena has delivered. \3

Indeed, Kadena's Chainweb protocol is built on trustless non-interactivity, which is impossible for a PoS network. As PoS shards increase, the pressure to stay online grows. With Chainweb, there is no difference between 10 or 10,000 chains for consensus or security. \4

Industrial-strength scalability can't be faked. Only Kadena can scale to any load, any sharded PoS system will grind to a halt with enough shards and experience massive security breaches. By solving for scalability, Kadena finally unleashes blockchain for universal adoption. \end

***

Scalability must come with security AND decentralization. Layer-2 is always a trade-off

Layer-2 is the best way to get fast finality. Kadena Kuro provides a lightning fast layer-2 rail that leverages public Kadena POW for settlement. Kuro's ScalableBFT protocol handles 1000s of validators without slowing down, so you can ramp up layer-2 security as needed.

Sure, Pact is easier/safer/cheaper than Solidity, but here's the thing: it needs to be, because smart contracts are HARD. You're deploying a business model, not just code. Worrying about gas, exploits, and scaling just slows you down

***

Kadena is layer-1: think Eth 2.0 but with scalable proof-of-work and a better smart contract story. Rollups are layer 2, compare to Lightning network: moving work offchain for speed but sacrificing security, transparency, and decentralization.

***

PoS boosters like VitalikButerin are impossible to debate. PoW is simple and proven, even kadena's scalable PoW is an incremental step from Bitcoin. Meanwhile every PoS flavor has endless obscure doodads to hide the glaring fundamental weakness of a plutocratic design.

With the success of PoW Ethereum and mega-wealth for insiders, perhaps it's no accident that Eth 2.0 is forever delayed. Casper v1 PoS could have shipped years ago, but that would put ETH at risk. They know PoW is more secure.

The ETH2 "delays" are no accident. Ethereum killed the Casper POS upgrade in '16 to protect the POW ETH golden goose, followed up with the most complex upgrade path possible to say "we're working on it" while enjoying the security of POW. Better to just scale POW like

"PoW is state-of-the-art security."

***

https://collectednotes.com/kadena/kaddex
