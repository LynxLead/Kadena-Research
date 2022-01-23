# PACT

The most important aspect of Kadena is PACT, pact is a smart contract language and it's the most powerful tool for creating applications on a blockchain, pact already contains all of the features that other projects say they will develop eventually, including full Formal Verification of user code, error messages, contract upgradability, multi-signature, and support for interoperability

It's so easy to read and write that a technical lawyer can reliably program his smart contracts with a little practice just like he could learn to manipulate data in Excel, formal verification which is invaluable when you are dealing with critical systems i.e. those that handle a lot of money or play a key part in infrastructure, Turing incomplete (prohibits recursive function calls, unbounded looping and variable reassignment which eliminates the potential for exploits that have ravaged EVM languages by design), upgradeable contracts whereas Solidity contracts are final and require proxy contracts etc. It's a next gen smart contract language that improves upon Solidity much like Chainweb is a next gen blockchain that improves upon its POW predecessors.

Pact will be established as the global standard of smart contract development. Cosmos already has pact and Polkadot wants to work with kadena, this is just the beginning and the goal is for pact to be on every chain that matters.

***

Pact's smart contract governance can be "code is law" (autonomous), or multi-sig, or representative, whatever the devs build. Pact is "code-on-chain" -- users read the governance code directly. On EVM chains it's whether the dev chose to upload code or not. Pact empowers DYOR

***

Pact, unlike something like DAML, was always supposed to be an easy-to-adopt standard for smart contracts by other chains. Pact **is** a competitive advantage, but that's because we were the first ones to figure out what will be the standard vs the only ones that can use it. Any project that wants to adopt/incorporate it gets our full support. We're hopeful that it becomes the lingua franca of safe smart contracts so that the entire industry can move forward from the Proof-of-Concept that is Solidity. Seriously, at this point Solidity/the EVM is just holding crypto back.

***

Pact smart contracts can be autonomous/non-upgradable if the devs choose. Remember btw that every major smart contract on ethereum now uses a proxy to rug pull at will. In the end you have to DYOR which means checking contract governance. Autonomous is great, until a bug or hack steals all your coins. Upgradeable is great but you should understand that governance before you buy in. There's no free lunch. With Pact you can always check the governance code yourself -- and you should.

***

1. The next issue is more subtle: _smart contracts must interact with each other in a single transaction_. True business on a blockchain doesn’t make sense if all you can do on blockchain are tokens, because you merely end up with a ledger of some stuff that you can trade back and forth and little more. Though a necessary feature, tokenization isn’t sufficient for serious business adoption. With Kadena’s stack, you will be able to chain various token workflows together into a larger functional workflow. Your linked Pact smart contract could get a dozen things off a site like Wish, handle the FedEx shipping to a service like Rent the Runway, handle the cleaning, and then also handle shipping it to you as well.
2. Another critical problem is one of trust and control: _smart contracts must be safe_ _**and**_ _upgradeable._ One of the biggest problems with the sharing economy is trust — some people don’t like the idea of sharing their car with a stranger if they can’t control their use. That issue of control and trust an even bigger problem for companies. Kadena’s safe smart contract language Pact comes with upgradeable governance–the ability to designate how and who can change that contract–which allows you control over the ledger so that even if trust breaks down, you can actually fix things. If a dependent service ends up being malicious, you can upgrade your contract to cut them out of the system and upgrade the contract to fix the bug. Unlike generic APIs or database access controls, smart contracts preserve the intent of the creator without raising security concerns.
3. The final necessary feature is about permissions: _smart contracts must allow snapshotting imports_. Though a technical concept, this is what’s needed to get _smart contract interoperability_ actually working safely. The only way you’re going to get a company to take a core piece of their back-end and expose part of it to the public is if the company knows that, no matter what happens, only the code that they write will be running in anyone else’s contracts and only the code they explicitly bless to run inside their contracts will be allowed to run. There should be no way for someone to get arbitrary access to their database. Unlike other smart contract languages, Pact was purpose-built to be safe enough for business level adoption cases.

***

lockchains are a tamper proof data store, right? They function as a permanent record. We've made a lot of design choices in many areas that are debatable. But the one that I think is the most obviously better is the choice to put human readable source code on the blockchain. Ethereum is like saying, "Your honor, I submit exhibit A into the official record"...but exhibit A isn't even understandable by a human. Furthermore, you can't possibly get the original source code from the EVM bytecode that is on chain. You can only do it if the person who wrote it gives you the source code. Here's a talk that describes some of the benefits of Pact

***

In my understanding I see the following benefits of pact:

1. The code is stored on the chain interpreted and human readable, which makes it easy to verify and maintain. (sure that could be solved by other means with a byte code language, too, but pact has one possible solution)
2. It's fast and scales. State doesn't carry overly complex Merkle indexes. That has pros and cons, but I think the pros overweight the cons.
3. It's a domain specific language designed for the domains where we think smart contracts are most useful. Pact is not designed as a general purpose/universal language. That gives pact a lot of power and easy-of-use in the domains that it targets. In particular it allows pact to be more efficient.
4. Formal verification is build into the language. Again, this can also be done for other languages. But formal verification is generally infeasible and to become useful one as to constrain the domain -- which is precisely what pact does. In particular formal verification would be much harder and less useful for a more low-level and general language like solidity.

***

Kadena also has Pact, which is a smart contract language that was designed from ground up specifically for the needs of decentralized finance.

Most other widely used smart contract languages, like Solidity, are designed as general purpose, universal programing languages. That has the disadvantage that those languages are less suited for the special needs of block chains. However, it also offers almost no advantage, because in the heavily constraint execution environment of a block chain, many features of general purpose programing languages make no sense, introduce security risks, or are prohibitively expensive gas-wise.

The designers of Pact spent a lot of time to study existing smart contract languages and to learn from their short comings. Pact is focused just on the needs of smart contracts.

To me Solidity looks like the attempt to somehow port Java to a block chain. I guess, it would be well suited if you wanted to run a graphical desktop environment on a block chain. The creators of Pact worked at banks where they developed financial software.
