---
layout: post
title: Don't trust, verify.
---

With the launch of the [blockstream bitcoin satellite](https://blockstream.com/satellite/) service from Aug 2017  

{% include youtube.html id="lbx7NAnVeGc" %}

a number of new use-cases for Bitcoin started to become possible, at radically lower cost, globally and with better privacy. 

Some of the use cases were discussed on [blockstream's blog](https://blockstream.com/2017/08/15/announcing-blockstream-satellite.html) 
and on this Bloomberg interview - fun to interject the motivation discussion for fullnodes onto a financial news show.

{% include youtube.html id="EIHn1n4et38" time="1213" %}

skip to 14mins 20secs [youtube](https://www.youtube.com/watch?v=EIHn1n4et38&t=14m20s)

But one more subtle question I was asked at the [HODL HODL conference]({% post_url 2017-11-25-hodlhodl-riga %}) 
in Riga, Latvia was do users of the blocksat have to trust the transaction and blockchain data received via it.  In fact satellites are for the most part quite simplistic, in beaming down signals beamed up at them, so that the intelligence 
is in the teleport (the uplink ground station).
For the blocksat the uplinks run a fullnode connected via [Matt Corallo's](https://twitter.com/thebluematt) fast block 
transport [FIBRE](https://bitcoinfibre.org) protocol.  So the question was phrased as do users who receive bitcoin data via the blocksat have to trust the uplink Bitcoin fullnode operated by blockstream.

![telstar11n]({{"/files/telstar11n.jpg"}})

The answer counter-intuitively is no!  The reason this works is the bitcoin blockchain is a proof-of-work authenticated chain,
it is secure because you personally can verify the blocks are correct by running a fullnode, and verifying that you are receiving the corrrect version of the blockchain by sticking to the most-work valid chain version.

In normal operaation a bitcoin fullnode joins a peer to peer network, with typically 8 peer connections - consider the
related question if one of those connections was 100Mbit and the other 7 connections were 10kbit connections would you be 
reliant on the fast connection?  The answer is no because you would see the discrepency as headers are exchanged and 
then data - so your fullnode would refuse to follow a less work chain even if the faster node was confused or malicious.

The trust model is the same with the blocksat - users can and should verify the blockchain via other slower / more expensive channels.  For example check blockheaders via GPRS data, via SMS etc.  The headers are enough to verify the proof of work, 
and the bulk data to verify the transactions and blocks can be sourced via the satellite feed at no incremental bandwidth cost.
