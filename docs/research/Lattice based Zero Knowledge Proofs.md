---
title: Lattice based Zero Knowledge Proofs
createTime: 2025/03/05 14:51:05
permalink: /article/fkbnx5lh/
---
## Lattice-based Zero-Knowledge Proofs

Zero-knowledge proofs are an important cryptographic primitive that allow a prover to convince a verifier that a statement is true without revealing any information beyond the validity of the statement itself. However, the security of most existing zero-knowledge proofs largely hinges on the hardness of the discrete logarithm problem, rendering them vulnerable to potential threats posed by quantum computers. To resist quantum attacks, lattice-based cryptography stands out as a leading contender among post-quantum alternatives.

We have conducted research on the following topics:

- Lattice-based RingCT Protocols for Anonymous Blockchains: By introducing new techniques for range proofs and (linkable) ring signatures, we propose more efficient RingCT protocols within lattice settings.

- Lattice-based Sigma-Protocols with Standard Soundness: Extending the sumcheck-based norm enforcement in LatticeFold [BC24], we develop efficient Sigma-protocols for polynomial relations that achieve standard soundness.