# 2. Hashing

Why should we learn about encryption hashing?

The `private-public key pair` is a metaphorical passport to participating in transacting on the blockchain. Similar to how you learn to use a credit card, secure it and protect it. ___You need to protect the private key for the security of your assets on the blockchain.___

In this lesson, we learn `hashing` that plays a critical role in the blockchain process, and also in the integrity of the transaction and confidentiality of data. 

You'll keep hearing the words: hash rate, hash power, hash this, hash that frequently in the `blockchain world`. For these reasons, you ought to have some basic understanding of `hashing techniques`.

The primary goal of this lesson is to provide you with this knowledge.

## What is `hashing`?

A `hash function` or `hashing` __transforms__ and __maps__ an _arbitrary_ length of input data value to a unique _fixed_ length value.

`Input data` can be a `document`, `tree data`, or a `block data`. Even a slight difference in the input data would produce a totally __different__ `hash output value`.

The following are two basic requirements of a `hash function`.

- The algorithm chosen for the `hash function` should be a __one-way function__ and
- It should be collision free, or exhibit extremely low probability of collision.

The _first_ requirement is to make certain that no one can derive the original items hashed from the hash value. Can you make potatoes out of mashed potatoes? 

The _second_ requirement is to make sure that the `hash value` uniquely represents the original items hashed. There should be extremely low probability that two different datasets map onto the same `hash value`.

These requirements are achieved by choosing a _strong_ algorithm such as `secure hash`, and by using appropriately large number of bits in the `hash value`.

Most common `hash size` now is __256 bits__ and the common `functions` are __SHA-3__, __SHA-256__ and __Keccak__.

## Hash value space

__Q__: How good is 256 bits hash?

A `256-bit` hash value space is indeed very large. 2 to the power of 256 (2^256) possible combinations of values. That is approximately 10 to the power of 77. That is 10 followed by 77 zeros (10^77).

Odds of a meteor hitting your house is higher than generating two of the same hash values of 256 bits when applying this algorithm.

Great. Let's proceed to explore some techniques now. We'll compare two different approaches for `hashing` based on how the constituent elements are organized. A simple `hash` and a `Merkle tree hash`.

Here we illustrate simple `hashing` and `Merkle tree hashing` with ADD as a hash function. We use the data `10`, `4`, `6`, `21` and `19` and `ADD` as a hash function. Actual hashing functions are quite complex and are variations of `SHA-3`, and the data values are much larger, mainly 256 to 512 bit values.

In the simple hash approach, all the data items are linearly arranged and hashed. In a tree-structured approach, the data is at the leaf nodes of the tree, leaves are `pairwise hash` to arrive at the same hash value as a simple hash.

## When is a simple hash or tree structure used?

__Simple hash__:

- When we have a fixed number of items to be hashed, (such as the items in a block header)
- We are verifying the composite block integrity (not the individual item integrity)

__Tree structure__:

- When the number of items differ from block to block , for example, number of transactions, number of states, number of receipts, we use the tree structure for computing the hash.

Note that the state is a variable that may be modified by a `smart contract` execution, and the result of the execution may be returned in a receipt. We'll learn more about their use in course two.

__Tree structure__ helps the efficiency of repeated operations, such as transaction modification and the state changes from one block to the next. Log N versus N. 

## Summarizing

In Ethereum,

- `Hashing functions` are used for generating
    - `account addresses`
    - `digital signatures`
    - `transaction hash`
    - `state hash`
    - `receipt hash`
    - `block header hash`

- `SHA-3`, `SHA-256`, `Keccak-256` are some of the algorithms commonly used by __hash generation__ in blockchains. 


## Resources: Hashing

The following resources were selected to provide an overview of the topic of Hashing. We would like to acknowledge the authors of the various web articles, videos, and papers for their insightful discussions and analytics which help formed the basis for some sections of the lessons and modules.

Title of resource: [What Is Hashing? Under The Hood of Blockchain](https://blockgeeks.com/guides/what-is-hashing/)

- Resource type: Website
- Description: An article that not only explains the basics of hashing but introduces a more specific type of hashing and how it affects the mining process.

Title of resource: [SHA: Secure Hashing Algorithm - Computerphile](https://www.youtube.com/watch?v=DMtFhACPnTY  )

- Resource type: Video (Run time- 10:20)
- Description: Dr. Mike Pound explains how files are used to generate seemingly random hash strings.

Title of resource: [Hash Functions](https://www.cs.hmc.edu/~geoff/classes/hmc.cs070.200101/homework10/hashfuncs.html)

- Resource type: Website
- Description: Explanations and examples of simple hash functions and the hashing sequences of characters.

Title of Resource: [Blockchain demo](https://anders.com/blockchain/hash.html)

- Resource type: website
-   Description: This website contains a hashing tool.