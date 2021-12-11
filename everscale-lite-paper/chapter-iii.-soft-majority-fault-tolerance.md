# Chapter III. Soft Majority Fault Tolerance

Now let's talk about security guarantees. If there is one chain where all the validators validate everything, then obviously the security guarantee for this network is the combined stake of all of its validators. Basically a lot of validators equals a lot of security guarantees. If, however, we start dividing them by segments such guarantees decrease.

And if these segments are split into even smaller ones, the security guarantees decrease to unsustainable levels, which means that corrupting the block becomes financially viable for scammers and rogue validators. The corruption will go undetected for some time because other validators will not run this computation. So they won't know a scam has taken place.

The proposed way to deal with this was —  let's have fishermen.

What fishermen do is they validate some blocks. And then one of them may detect that the wrong block was produced, which they can actually prove. With this proof, they can get some reward and the network can slash the validators. But there was a problem with that approach. When the fisherman finds this wrong block, it may be just too late. The rogue validators can submit a very large fake transaction, and then do something with that transaction before anyone has noticed. So for example, they can double spend: create tokens out of thin air, send this money to some smart contract of some exchange and sell the tokens to those of another network, before running off with the money. And they can do all that before fishermen will ever know and catch the block. This is because fishermen are probabilistic. They do not validate every block; submitting the proof and slashing the validator will take time and will not reverse everything the validator did. And the scam will, of course, be much more valuable than all the combined stakes of all validators that will be slashed later on. And that can have catastrophic consequences on the network. Simply put, we can not rely on fishermen. And it doesn't matter if the blocks are corrected afterwards, because someone already suffered a lot of losses, for example, the exchange or the bridge.

So what can we do in order to verify any wrong block before it will ever be submitted to the network? In Everscale there is a protocol we call “Soft majority fault tolerance” SMFT for short. And we'll describe it very simply now.

![](https://lh4.googleusercontent.com/Vm-OzuEsy4BcGH9vt16lMhzKyaG\_OjXc4mZk2qYU\_ue-3c2Ya5pSbL8CriuyHBtcIjH188CszuxmE7XyFdYSTwuxsNwSqxIBPOvkE2tGIQK\_qONBGqxWvYrHXXHptz8TBAJ-7dRV)

A Validator who proposes a new block is called a Collator. The Collator will produce a block and send it not only to thread validators but to all validators. And that's normal because we remember the data here is the same. So now all of the validators have all of the blocks, even if they don't all validate them. Then, through the wonders of algorithmic science, each and every validator will run a calculation on that block hash. Through this, a few out of all validators will now need to validate this block in addition to those traditionally in their purview. We call these validators — Verifiers. The function that calculates who the verifier is, is random. The collator can never know which of the other validators will be verifiers. As a result, they can neither cheat, nor collude because they will need to collude with at least 51% of the network. And if 51% of the network agree to collude, it's no longer an attack. It's the correct network. If 49% think that the block is wrong and 51% think that this block is correct: this block is correct by definition. Therefore the chances of the collator to predict the identity of the verifier (even if the collator is in cahoots with 50% minus one validator of the network) are so small, the attack is never probabilistically successful. Thus the collator will never propose a wrong block because the collator's chances of succeeding with this attack is mathematically lower than in trying to corrupt Bitcoin.

![](https://lh3.googleusercontent.com/6piHw2TuZS6DtlRUOxd0t2JWhODUb8TauNiFdg9HHdV-7Xn3WmGYxayNKfk1p1z6dnOp1wzibBg2ZWVZcvi0Ec\_\_Hz5How3F9aNmn-ctG9SV9uE06AiOr1WAuIWQyJx20hfynrF2)

Of course there's one small problem: we need to be sure that this block has, in fact, been transmitted to all the validators. In order to ensure that there is another protocol, which proves the block propagation and it's called Broadcast Protection Protocol. This protocol ensures that we can prove that a block has been transmitted to at least 51% of all the validators. Once we know that, we know that the attacker can never be able to predict, with a high enough chance, who the verifier is within 51% of the validators. If the Verifier finds a rogue block there is a procedure on how this block will be stopped and checked by a lot of other validators to be really sure that this block is wrong or correct. Now, we also ensure that post factum we know who the verifiers of the previous blocks are, and if the verifiers did not perform their job will slash them as well. So they will be penalized if they didn't verify the block. So, the collator cannot also assume that verifiers will be lazy enough to not validate blocks.