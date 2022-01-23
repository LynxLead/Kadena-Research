# Privacy

KDA has no native privacy features. This is both because the tech, heck the core math, is still in its infancy. Anything beyond a zero knowledge balance transfer is incompatible with production requirements, ergo smpc smart contracts are out simply for performance reasons alone. Even if a general purpose privacy solution were feasible, it's incompatible with the existing global regulatory environment even when you stick to just privacy coins. And privacy coins too are quite new and prone to exploits/shortcomings.

Pact does implement double ratchet (what signal uses) but it's only enabled on permissioned chain deployments because it's used for creating encrypted communication channels (and thus tables that aren't globally replicated). On permissioned chains this use-case holds water but it doesn't work on public chains.
