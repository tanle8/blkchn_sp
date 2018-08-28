# Algorithms and Techniques

## Public-Key Cryptography

### Introduction

Two techniques are predominantly used for securing the chain and for efficient `validation` and `verification`. __Hashing__ and __Asymmetric key encryption__.

These techniques depend on several complex proven algorithms. We provide a high level view of the application of these algorithms, and the critical role they play in securing the decentralized chain in the four lessons of this module namely; Public-key cryptography, secure hashing, transaction integrity, and block integrity. We'll begin this module by discussing the concept of asymmetric key encryption, then we'll define the concept of hashing, followed by the algorithms used for various hashing needs of the block chain protocol. We then explain the techniques that use these algorithms, to manage the integrity of the transactions and the blocks in a block chain. Learning outcomes of this module are; to summarize the working of the Public-key cryptography, explain simple hashing and Merkle tree hashing, explore the application of hashing and cryptography in protecting the blockchain. 

### Recall:

- Blockchains decentralized network participants, are not necessarily known to each other.
- Credentials cannot be checked by the conventional means such as verifying who you are with your driver's license.
- Participants can join and leave the chain as they wish. They operate beyond the boundaries of trust.

### Question:

Given this context:

- How do you __identify__ the `peer participants`?
- How do you __authorize__ and __authenticate__ the `transactions`?
- How do you __detect__ `forged` or `faulty transactions`?

We can do these things by using `Public-key cryptography algorithm` that we'll discuss in this lesson.

Let's begin by examining simple `symmetric key encryption` - The same key is used for `encryption` and `decryption`, so it is called `symmetric key`. 

Example, `Ceasar encryption` is the simplest one with alphabets of a message are shifted by a fixed number, and this number is called the `Key`.

In this example `F` is a function defined by shift by three in alphabet. Consider, "Meet me at the cinema." You shift by three the S key value of every letter to encrypt it, and your receiver decrypts it using the same three as the key. Shift the other way every character to view the original message. Three is the key in this trivial example. Since the same key is used for encryption and decryption, it is a symmetric key.

Note that the key and the encryption and decryption functions are typically much more complex in a real application.
Note that symmetric key encryption has issues:
    - _number one_, it is easy to derive the secret key from the encrypted data.
    - _number two_, the key distribution, how do you pass the key to the participant transacting?

These issues are further exasperated in a `block chain decentralized network` where participants are unknown to each other. Let's now examine how `Public-key cryptography` addresses these issues.

Instead of a _single_ `secret key`, it employs ___two___ different `keys` that take care of both the issues of `symmetric key encryption`.

Let, lowercase `b` uppercase `B` be the `private public-key pair` for a participant in __B__uffalo, New York USA.
Let, lowercase `k` and uppercase `K` be the `pair of keys` for the participant and __K__athmandu, Nepal.

`Public-key` is published, `private key` is kept safe and locked. Typically using a `passphrase` and the `pair` works as follows:

- Encrypting function holds two `properties` with a `key pair`.
- The `public-key private key pair` has the unique quality that even though a data is encrypted with the private key, it can be decrypted with the corresponding `public-key` and vice versa.
    
Now let's look at an example, __authenticate the `sender` and the `receiver`__. We'll examine just one common use of a `symmetric key encryption`. Let's say a participant in Buffalo wants to transact with the participant in Kathmandu.

- Instead of sending just a `simple message`, a participant in `Buffalo` will send a `transaction data` __encrypted__ by `Buffalo's private key`, and then __encrypted__ by `Kathmandu's public key`.
- Kathmandu will first __decrypt__ the data using its own `private key`, then use `Buffalo's public key` to __decrypt__ `assigned transaction data`.
- This ensures that only `Kathmandu` can __decrypt__ and __receive__ the data and that only Buffalo could have sent the data.

 A popular implementation of `public key, private key` is the `Rivest Shamir Adleman` (__`RSA`__) algorithm. Common application of RSA is the ___passwordless__ `user authentication`, for example for accessing a virtual machine on Amazon cloud.
 
 Though RSA is very commonly used in many applications, block chains need a more _efficient_ and _stronger_ algorithm. Efficiency is a critical requirement since public key pair is frequently used in many different operations in block chain protocol. `Elliptic Curve Cryptography`, __`ECC`__ family of algorithms is used in the `Bitcoin` as well as an `Ethereum` block chain for generating the key pair.
 
 ### Why `ECC` not `RSA`?
 
 - ECC is stronger than RSA for a given number of bits.
 - Did you know that `256 bit` `ECC key pair` is equal in strength to about `3072 bits` of `RSA key pair`.
 - Both `Bitcoin` and `Ethereum` use __`ECC`__ based algorithms for their encryption needs. 


## Resources: Public-Key Cryptography

The following resources were selected to provide an overview of the topic of Public-Key Cryptography. We would like to acknowledge the authors of the various web articles, videos, and papers for their insightful discussions and analytics which help formed the basis for some sections of the lessons and modules.

1. Title of resource: [What Is Public-Key Cryptography?](https://www.globalsign.com/en/ssl-information-center/what-is-public-key-cryptography/)

    - Resource type: Website
    - Description: A look at the encryption algorithm and its security benefits

2. Title of resource: [Asymmetric Cryptography (Public-Key Cryptography)](http://searchsecurity.techtarget.com/definition/asymmetric-cryptography)

    - Resource type: Website
    - Description: Article explains what Asymmetric cryptography is and how it works

3. Title of resource: [Public Key Cryptography - Computerphile](https://www.youtube.com/watch?v=GSIDS_lvRv4)

    - Resource type: Video (Run time- 6:19)
    - Description: Youtube video that explains how public key cryptography works.

