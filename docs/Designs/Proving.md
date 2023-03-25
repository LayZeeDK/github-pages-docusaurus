---
sidebar_position: 2
---

# Proving MXC Blocks


## Zero-Knowledge Provers

The purpose of proving blocks is to allow bridges to withdraw state out of the rollup. 

To rely on some state that happened inside of the rollup, a bridge will want a proof that everything was done correctly. On MXC zkEVM you can run a Supernode as a prover and prove blocks, permissionlessly. 

This means that you can examine the proposed blocks on the MXCzkL1 contract, and generate proofs for them. Currently, any prover can create proofs for proposed blocks. This means that the number of "fork choices" has no upper bound, because we don't know what is the correct state transition yet. 

Only first prover with a valid proof of the correct fork choice (state transition) will receive the reward of MXC.

## Zero-Knowledge States

There are three states that a block can be in on MXC zkEVM:
- Proposed
- Proved
- Verified

For the visual learners here is a visualization of the three stages (proposed -> proved -> verified)

![States](/img/proving.gif)

