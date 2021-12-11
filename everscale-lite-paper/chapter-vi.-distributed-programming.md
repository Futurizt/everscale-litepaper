# Chapter VI. Distributed programming

What is this distributed programming we’ve heard so much about? On blockchains today wallet addresses are associated with a public key, derived from a private key. The address can contain a smart contract code or not contain anything at all and just be used for a native token.

On Everscale, however, the address is not associated directly with a public key, and must instead be associated with a smart contract in order for someone to be able to use it. Money can still be sent to any address, but those tokens will just sit there without anyone having any possibility of doing anything with them until smart contract code, a program that runs this money, is attached.

In that sense, Everscale is a definitive smart contract platform because every address is a smart contract. But more interestingly, this address is a result of a calculation which hashes the initial data and the code of a smart contract. For example, inputting the public key along with the contract code of a wallet, will output an address. However, if a different wallet's smart contract code is input, then the output will be different. There are therefore infinite amounts of addresses that can be derived for a single public key.

This opens very interesting possibilities, and has many positive implications. Let us take an example of how filenames run on Everscale.

Let’s say we want to resolve the name Everscale inside the Everscale blockchain. For this we use the decentralized name service certificate smart contract (DeNS). This is a smart contract associated with a certificate service, used to resolve addresses, similar to how today's browsers work. However in this case it just needs to be downloaded once, and can be used to resolve locally any name in the domain, without a need for a server. All it takes is for this certificate to be opened in a browser, the word ‘everscale’ to be typed and, because the address is just a function of instant hashing, in fractions of a second, the address appears, having been calculated on a machine locally.

This is the best decentralized name service in use today, entirely operating without servers. When we talk about distributed computing, we think of Everscale as a sort of a distributed decentralized key value database.

![](https://lh6.googleusercontent.com/iR-dPbvmHZkq-IdwgmgXVBhNMDKsAvBBRXNBwcGo-cHdzNTSikvH7vC51U6tk1EUX3vE4gLh6PV5OeOvoIdNwKYow-vz9nASOBx5AgRyssuTR92p9ezflr6M7vZ7PK0u\_UNNwHgm)

\
