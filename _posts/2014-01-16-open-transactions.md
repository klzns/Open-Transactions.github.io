---
layout: post
title: "Open-Transactions"
tagline: "Introduction"
description: ""
category: "introduction"
tags: ["Bernhard Müller Hug"]
---
{% include JB/setup %}

In order to write about Open-Transactions I will elaborate on some features of Bitcoin first. Bitcoin is a completely transparent protocol, a scarce resource, a community, a payment system, a commodity, a unit of account, a ledger plus a lot more. It currently raises a benchmark for what is now called cryptocurrency or digital money.

Bitcoin behaves like a commodity in a sense that one cannot have a negative balance just like one cannot have a physically negative gold balance. Within the Bitcoin protocol there is no way to lend or owe anyone Bitcoin and transactions cannot be reversed.
The current world markets trade commodities and resources without physically moving them though. This is achieved with the help of tokens which are denominated in the commodity. The system is based on trust in the issuer of the tokens. He has the commodity available according to terms agreed.

<!--more-->

Conducting business involves trust and I don’t see that technology would ever make trust obsolete.
Bitcoin is an ingenious invention and designed to securely hold and transfer value without relying on trust. There are no intermediaries for transactions and there is a mathematically defined money supply.
Bitcoin doesn’t suffice, however, to make a free market or a whole onpen and distributed economy.

Naturally there is some open source development around integrating a trust based economy with the currently available blockchain-based Cryptocurrencies and their 2nd layer features like [Colored Coins](http://coloredcoins.org/).
A very promising looking movement is Open-Transactions. It allows anyone to issue tokens and contract with one another in a distributed way based on cryptography and encryption.

This is possible through receipts for each action which are signed by all participating parties followed by a notary-server. It is the signed receipts you get back from this notary-server which hold value and are verifiable by any present or future notary or participant. The notary-servers are federated in a distributed network. Receipts are destroyed for new transactions (like a paper torn up) which leaves the user with only the newest receipt.
The servers only sign what was signed by the participants already and cannot alter any balances or agreements. The servers can freely set their notary fees and compete against each other.

Smart-contracts are used to define the tokens. The issuer can write the smart-contract as he wishes. Through the smart-contract he defines what the tokens will behave like. He will only have privileges if they are described in the contract. Anyone can look at the token and accept it or not.

Smart contracts further allow for several parties to have computationally scripted financial interactions. E.g. escrow, loan and hopefully [Nash](http://nashx.com/HowItWorks) equilibrium exchange. These contracts can be set up with the help of a template but are totally user definable. They contain script language as well as any comments in plain text.

Open-Transactions allows for different kinds of token transmissions. A straight transfer, a check or cash transactions. It allows you to trade tokens with anyone through various market features and to also discover the people who want to trade also.

It even becomes possible for a closed community to barter for all goods within their community in a secure and legally binding way. This can even be done without the involvement of any currency. Lets walk through an example of this. You are a fisherman and I am a carpenter:

> I repaired your boat and you want to pay me with 100 herrings as this is most convenient for you. I accept that but I don’t want to have 100 at once as they will go off before I can eat them. So we might settle for a currency (at least partially) as this seems to resolve the issue. Alternatively you can issue 100 herring-tokens on Open-Transactions and transfer them to me. Your balance will be -100 mine will be 100. Anytime I need some herring I can come back to you and redeem 10 of them. You accept these 10 herring-tokens and give me the fish. By doing this your balance will go to -90. After some time I might get bored of eating herring and therefore trade some of these for apples. The villages apple farmer will be able to redeem the herring tokens he got from me because you will know that these are herrings-tokens issued by yourself and that I will have less after giving some to the apple farmer. You are happy to hand out some fish and accept the tokens for them. In the same way the apple farmer will give my son an apple if he turns up with an apple-token I handed out.

Doesn’t this sound like the features some economists are missing with Bitcoin?
Open-Transactions might just become the ultimate open and distributed finance suite available, accessible for everyone connected to the internet. The concept with the federated notary-servers signing receipts might be a true game changer.

So you might ask where you can download OT for desktop or mobile OS? Well it is not entirely ready just yet if you are, like myself, not so much into building from [source](https://github.com/Open-Transactions/Open-Transactions). Patience will hopefully reward us with an installer sometime soon. Meanwhile you might want to study the [Open-Transactions Wiki](http://opentransactions.org/wiki/index.php?title=Main_Page) which has a lot of great explanations. Stay tuned.

by Bernhard Müller Hug