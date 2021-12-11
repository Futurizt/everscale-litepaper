# Chapter VII. Gas & fees

We're moving now to the question of Gas and fees, as well as, more generally, economics. There are two types of fees. Storage fees and processing fees, called Gas. While there are pretty complicated fee structures in Everscale, we're not going to talk about that in all too much detail. What is important here is how much users pay.&#x20;

We know that with the number of transactions in the network increasing, the Gas fees increase as well. This is because of network congestion. This potential for congestion means fees cannot be arbitrarily low, to protect the network from an attack where someone buys it and stops it entirely for a low price. So in order to have really low transaction fees, the network has to be really scalable. That's just a matter of arithmetic.

We have such a network. So let us discuss how the fees are going to be structured.

Let’s take a MasterChain with a WorkChain on top of it, which has threads in it. This WorkChain has a current network capacity of around 10,000-12,000 transactions per second. In the beginning, the gas fees are naturally going to be very low because the volume of transactions offsets any potential congestion. However as the network grows, and starts becoming congested, Gas prices begin to increase. Why? Because we are already anticipating that we need new validators for new WorkChains that we need to set up. In order to do that, we need to start collecting fees in order to incentivize new validators to join the network.\


![](https://lh3.googleusercontent.com/83DLJ\_BGkt8HcnMx2T0OCpoZROzd\_JJau2ReoDKj69K-XYUm-s8x-CozgwnIXn7bNU3Vwu7EMEJUF-fupDtOWzLdALtqaQcplRK9LP6XN1TDngAKnmw-TGLRR4gbEBDZvIYcN3A8)

Eventually, as a result of this, Gas prices will increase significantly. But only for a very brief period of time. Because at this point there will be a lot of demand to start a new WorkChain and a lot of funds to do so. Once new validators join the network, a new WorkChain will be established, doubling the volume of possible transactions and balancing the network. This is a load balancing mechanism. Once the second WorkChain has started, the fees naturally return back to their original point, very close to zero. Periodically, with growing congestion, Gas prices will rise, a new WorkChain will be set up, and they will again fall rapidly. Everscale can add WorkChains without end, until the world basically runs out of available servers or available internet capacity. By which time, of course, all the Internet will be decentralized.
