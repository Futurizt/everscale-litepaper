# Chapter II. Sharding and Multithreading

Everscale is the only blockchain which operates through both sharding and multithreading. Let’s see how it works.

So if many validators have just joined the network, they need to validate something. So each validator is assigned a chain to validate on. These can be MasterChain or WorkChains. All these chains are separate blockchains, containing many other separate blockchains, as we will see. The difference between MasterChains and WorkChains is that all block proofs from all chains are submitted into the MasterChain. All blocks in a given MasterChain are collections of proofs that the WorkChains connected to it are working correctly. This part of the design is similar to Ethereum 2.0 or Polkadot for instance, but here the similarities end.

Validators are assigned to one of the chains, and they can see all its associated data; they download, store, and change the state of all the programs and some other parameters of this particular chain. This is sharding. Sharding is a separation of data, and the term comes from the database world. And that means that these validator servers do not store the state data of another chain, it’s therefor sharded.

![](https://lh6.googleusercontent.com/nxPth764Aj-EvGqjWB8OdPxsAN7jEVITMn5upb4R98gy1j23czp4VUK0b-6lhynOxDPsRQJ8Di8d3QsgL9WYUpPVqMDqwOe1rQ00BGeCZ4rBNiLT14zadYaW6PkfUbYPGqkOVvuc)

Yet just to shard the data is not enough to ensure scalability, because sharding of data does not provide the network with the ability of parallel execution of smart contracts that need to be executed on a particular chain at a high enough speed.

There is also a need for a parallel program execution on top of sharded data to ensure true scalability. There are two things that constrain scalability. The first is when there is a need to send a lot of messages between servers: at a certain point the internet connection simply runs out. Once that issue is solved with sharding it's the processing power that starts running out. The solution to this conundrum is something we call multithreading or, basically, parallel execution.

All our modern computers run multi core processors simply because single core cannot execute all the programs in parallel because they just hit certain limitations, namely, the laws of physics. Everscale does the same thing for its virtual processor. That is done with each validator of the same WorkChain being assigned a thread. So there are groups of validators that execute different sets of smart contracts, which are separated by accounts. That's precisely why we have infinite scalability: because we can now add these validators linearly, as more programs we need to execute.

![](https://lh5.googleusercontent.com/jP9iVXnVvSvFFleIz8VnHU6lzriq0vruLkvant6aPsRW2dSxlERfLW4YusDnUqiF6rf2BF23w3QkWAG1ktjlM7oFo65LyshSFMmMakHZpjsftBXnVxA6zqHFRodIwctF6pddF4Rd)

We can add more WorkChains and more threads. And all of that happens dynamically. When we don't need to execute too many programs, there will be fewer threads, and just on the one WorkChain, for example. But once the number of smart contracts which are executed grows and there is a need for more and more processing resources and disc space, more chains and threads will be added.

And, that's how it scales. And that's why it ever scales. And, as long as you don’t run out of all servers in the world and all the internet capacity in the world, Everscales.
