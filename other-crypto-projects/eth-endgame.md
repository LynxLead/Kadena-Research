# ETH ENDGAME

I get that it says "it's centralized but still censorship-resistant" all over the place, and motivates the claim by saying there's a bunch of future tech and mitigations to avoid censorship... and yet at the end of the day we're still talking about taking a multibillion-dollar payments layer that's unregulated due to being decentralized and centralizing its payment processing layer (not validation/settlement), to the point that the layer becomes smaller than VISA. And somehow expecting a reg hammer to not drop on it once it goes live. I get that it's maybe possible to keep production censorship-resistant, yet all the "technically" arguments in the world can't stop a regulator with a small, finite list of payment processors to target My big question is this. Back when ETH 2.0 was first proposed, how to shard a POS blockchain was a completely unsolved problem. Now, however, there is NEARProtocol, which is in production. At least one of the following is true:

* A: NEAR makes worse trilemma-addressing tradeoffs than Endgame (e.g. Vitalik thinks NEAR doesn't work)
* B: ETH2 sharding isn't ever actually meant to ship and Endgame is the latest 5-year research project to placate the ETH community.
* C: ETH2 is suffering from "not invented here" syndrome and won't use NEARs approach because of vanity.

I'm having a hard time coming up with other explanations. For the record, if ETH were sticking with POW for scaling, I'd be saying the same thing but swap NEAR for Kadena.

\---

We're used to there being a ton of options/standards in tech, and yet when it comes to consensus there are only a few families of options: Nakamoto, Paxos, Snowball, etc... and onto each there are more (though still few) performance tweaks/scaling approaches: GHOST (ETH1), Chainweb (KDA), PoSpace (Chia), etc.\
Picking a family + tweak isn't really picking a winner or being opinionated, it's just about picking something that gets the job done.

ETH2 picking, say, polygon to bake into the core protocol would be closer to "picking a winner" but ETH2 following NEAR's approach to sharding is no different than ETH1 picking Nakamoto + GHOST, neither of which they invented.

That's what's weird about Endgame. It would _make sense_ for Vitalik to just say "we're copying NEAR first and then we're doing rollups after". It'd be exactly the same as ETH1 deciding to adopt GHOST to decrease confirmation time, except this would address scaling.
