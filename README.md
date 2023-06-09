# Zero Knowledge Identity Proxies in Noir

This repository is a research repository to explore how to use the Aztec stack and Noir language to provide proofs about identity, on-demand to DApps, without revealing the underlying accounts associated with a single user.

## Example problem

Like many ethereum users, I maintain several different wallet addresses that serve different purposes, for example:

- Hot Wallets for interacting with individual DApps
- Hardware and Multisig wallets for savings accounts
- ENS wallets and public wallets that I share frequently

Maintaining different wallets like this has a number of benefits: 
- You don't have a single point of failure if one wallet is compromised.
- Your entire net worth is not broadcast on chain for everyone to see.
- You can interact with new or experimental protocols with more confidence
- You can separate distinct identities when interacting with different communities.

![image](https://github.com/jordaniza/zkip-noir/assets/45881807/61bca7f2-6b22-4231-9bb0-cc019e560fa0)

One of the problems with this though, is that it's difficult to build a reputation on any one wallet. In order to maintain privacy and separation, the wallets can't interact with each other, and so for DApps and protocols, your new wallets have limited or no history. 

When I look at the potential for identity platforms in blockchains, I see this as a potential limiting factor in their usage - not all users will want to make their carefully separated identities publicly linked.

On the other hand, if users with strong identities can leverage these in some way (for example, UC Loans or airdrops may have identity requirements), it would be a shame to exclude people for whom privacy is a major concern. 

## Exploratory Solution

On idea to solve this would be to explore the use of Zero Knowledge Proofs to generate provable statements about a user's associated private wallets, that can be then associated with a public "Proxy" wallet.

![image](https://github.com/jordaniza/zkip-noir/assets/45881807/8d51015f-9b63-4a02-9773-f261b83b95a5)

Some examples:

- The owner of this proxy wallet also owns a specific NFT
- The owner of this proxy wallet has a total balance of at least 20 ETH in another wallet
- The owner of this proxy wallet has been using this network (has an historical transaction) greater than 100k blocks ago.


In an example workflow, if a DApp or Protocol requests some information about a user to qualify them for an airdrop. In this case, a fresh proxy wallet can be created, and a ZK Proof can be signed/generated* by a user's other wallet. 

The proof then be submitted by the proxy wallet, verifying the fresh wallet is, indeed, associated with a certain target user.

### Intial Research

@joshc helpfully provided some initial ideas in the [HackMD linked here](https://hackmd.io/@joshc/rJWgTMHLn#) after an Aztec office hours. Will continue to post notes and thoughts here.

* Mindful of Account Abstraction

## Aims

As mentioned, this is a research repo for a prototype/PoC. We're looking to explore and develop Knowledge about what the potential for ZK applications can do, and what the Aztec tech stack enables.

As someone who is neither a Noir, Aztec or ZK expert, this will be somewhat of a primer for me in these 3 new domains. There are no timelines nor a roadmap. Expect mistakes and jank. If you spot anything wrong, please let me know.
