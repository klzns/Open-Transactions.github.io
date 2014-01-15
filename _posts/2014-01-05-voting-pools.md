---
layout: post
title: "Voting Pools: How to Stop the Plague of Bitcoin Heists, Thefts, Hacks, Scams, and Losses"
description: ""
category: "voting pools"
tags: ["Justus Ranvier"]
---
{% include JB/setup %}

In July of 2011, the owners of popular web wallet service and payment processor MyBitcoin.com [absconded](http://www.reddit.com/r/Bitcoin/comments/k08a8/has_bruce_wagner_pulled_off_the_biggest_financial/) with all customer funds, almost 79 thousand bitcoins, and disappeared.

In March of 2012, several sites hosted with [Linode](http://arstechnica.com/business/2012/03/bitcoins-worth-228000-stolen-from-customers-of-hacked-webhost/)&nbsp;were hacked, including leveraged trading platform Bitcoinica, mining pool Bitcoin.cz, Bitcoin Faucet, and several other sites. A total of about 47 thousand bitcoins were lost.

Two months later, Bitcoinica was hacked [again](http://www.pcworld.com/article/255595/hackers_break_into_bitcoin_exchange_site_bitcoinica_steal_90000_in_bitcoins.html) and lost another 19 thousand bitcoins, causing it to shut down.

Two months after that, someone stole 40 thousand bitcoins from Bitcoinica's [Mt Gox account](https://bitcointalk.org/index.php?topic=93074), 30% of their remaining assets.

In September of 2012, exchange platform [Bitfloor](http://bitcoinmagazine.com/2139/bitfloor-hacked-250000-missing/) was hacked and lost about 24 thousand customer bitcoins.

In October 2013, [Silk Road](http://www.forbes.com/sites/andygreenberg/2013/10/25/fbi-says-its-seized-20-million-in-bitcoins-from-ross-ulbricht-alleged-owner-of-silk-road/) users lost 172 thousand bitcoins when they were seized by the FBI.

The months of November and December 2013 have been [particularly bad](http://www.dailymail.co.uk/sciencetech/article-2516024/Bitcoin-thefts-soar-online-criminals-target-easy-payday-currencys-value-quadruples-space-weeks.html) in terms of Bitcoin companies losing funds to theft, with Inputs.io, BIPS, Bidextreme all reporting losses.

In virtually every case of companies losing customer funds, it's difficult or impossible to disprove that an inside job was responsible.

<!--more-->

## Why Do Users Deposit Their Bitcoin With Third Parties?

After every event where customers of Bitcoin services lose bitcoins, experienced members of the community speak out and remind them that Bitcoin is designed for direct P2P interactions with no intermediary, and that handing bitcoins over to a third party is neither necessary or a good idea.

No amount of education and warnings, however, appears to be capable of convincing a majority of users to avoid doing exactly that no - matter how catastrophic the cost of doing so becomes.

There are several plausible reasons for this:

*   Users are getting involved with Bitcoin before they fully understand it, and assume that it works like the legacy financial system.
*   Users start out with a small bitcoin balance which they could afford to lose, become complacent, and then never change their habits as their holdings increase in value.
*   The software tools needed to secure Bitcoins properly are still developing and remain too hard for many people to use.
*   Certain services, such as exchanging between Bitcoin and legacy currencies, are difficult or impossible to implement without involving a centralized entity who holds all the funds.

While work is progressing on all fronts to improve the situation, it's unlikely that the paradigm will change any time soon. People will continue handing over their bitcoins to third parties, and will continue to lose funds to hacks and insider thefts, unless something changes to drastically improve the security of such arrangements.


## How Do Existing Services Work?

When you deposit bitcoin with a trading platform, or an online wallet, as far as the Bitcoin protocol is concerned, those bitcoins are no longer yours. Companies like Mt Gox, Bitstamp, BIPS, and Coinbase all have exclusive control over all customer bitcoins which have been deposited with them, and are fully capable of spending them as they wish. This may include returning the bitcoins you've deposited as promised, and may also include losing or stealing them, intentionally or under duress. The Bitcoin protocol can not protect you once you've handed your bitcoins over to someone else.

These services work by maintaining their own database that keeps track of how many bitcoins they owe to each customer. These databases can be as simple as a single MySQL table.

In all cases, whenever you deposit Bitcoin with a website, you're relying on their programming abilities to accurately track how many bitcoins they owe you, as well their ability not to be hacked, blackmailed, or extorted. Each site is unique in terms of how much programming effort they have expended towards tracking and protect your balance.

Is there a better way to track and protect customer balances than bespoke systems, systems which are sometimes developed as an afterthought since they don't represent the services' primary functionality?

## Open-Transactions

Open-Transactions (OT) is a financial cryptography library invented by Chris Odom, the co-founder of [Monetas](http://monetas.net/). It is designed to allow for secure formation and transaction of digital assets, smart contracts, and virtual corporations via cryptographically-signed receipts.

OT partially overlaps Bitcoin in terms of features, but has a different security model. Where Bitcoin is decentralized, OT uses federated servers. Bitcoin's security uses proof of work to prevent cheating while in OT it's possible for transaction servers to cheat, however the type of cheating they can engage in is limited to inflating the issuance of assets, since cryptographic signing means receipts can not be forged. This inflation risk is mitigated by a separation of powers and real-time auditing.

Asset issuers are independent of the transaction servers and the asset holders. If an audit discovers a transaction server attempting to spend inflated assets, the issuer can rescind that server's authorization to process their receipts, and can move to a new transaction server.

The Open-Transactions model will never provide the same security guarantees as the Bitcoin blockchain, however the security it does provide is substantially greater than any third party Bitcoin service can deliver to their customers, and it comes with compensating benefits in the form of a number of additional features not available in Bitcoin alone.

A transaction server in OT does what all deposit-accepting Bitcoin websites do already, in a more secure and transparent manner. Instead of merely storing a customer's balance in a MySQL table, OT provides the customer with proof of ownership in the form of a digitally signed receipt which is maintained current as assets are transferred or included in smart contracts.

Thus we can say, with apologies to [Philip Greenspun](https://en.wikipedia.org/wiki/Greenspun%27s_Tenth_Rule), "Any sufficiently complicated Bitcoin website contains an ad hoc, informally-specified, bug-prone, slow implementation of half of Open-Transactions."

## Voting Pools

The original intended use case of OT was to allow individuals to create and trade decentralized gold-backed virtual currencies, but recent development has focused on both using Bitcoin to add additional capabilities to OT, and also developing new capabilities which are useful to Bitcoin users and companies. One such forthcoming OT feature highly relevant to the goal of reducing Bitcoin thefts and losses is called the "Voting Pool."

A voting pool is a way in which multiple Bitcoin websites can collaborate to accept customer deposits in a way that makes theft vastly more difficult. Members of a voting pool do not accept bitcoins directly - instead they give their customers deposit addresses which require a supermajority of the pool members to cooperate in order to spend ([multisig](http://bitcoin.stackexchange.com/questions/3718/what-are-multi-signature-transactions) addresses). After receiving a deposit, the member then issues the depositor a BTC-denominated receipt. When a customer decides to make a withdrawal, she returns this receipt back to the issuer, and the pool votes to process the appropriate blockchain transaction.

What about this arrangement makes forming a voting pool a security feature instead of unnecessary obfuscation? There are several advantages to the voting pool:

*   It is no longer possible for an attacker to steal bitcoins by compromising a single server. Instead, the attacker would need to compromise almost all the servers in the pool.
*   This protection from attackers extends to insider threats. Even a malicious operator can not steal customer funds, since he can not forge customer receipts in the OT side, and the other pool members will not authorize a withdrawal without a valid receipt.
*   Since the members are operating from a shared pool of bitcoins, they have a very strong incentive to cross-audit each other. If they allow anyone to cheat it will affect every member of the pool For this reason, voting pools should include businesses which compete in the same space.
*   In addition to the protections from theft, customers will have far higher funds availability if they only do business with companies that use voting pools. If one server in a pool is down, the customer can still process a withdrawal through any other member of the pool.


## Effects on the Bitcoin Ecosystem

The introduction of voting pools to deposit-accepting Bitcoin businesses would virtually halt the occurrence of stolen funds. As the pools increased in size, the amount of internal auditing would increase, as well as the level of effort needed to compromise a service wallet. Once this level of protection became the norm, it would no longer be possible for scammers to start up a new site with the intention of collecting deposits and stealing them. Nobody would trust a site that did not join an established voting pool.

When voting pool functionality is ready for deployment, it would be enough if just three significant sites implemented it. Once these three sites started offering their customers cryptographic proof that their deposits were safe from theft, fully backed (not held in a fractional reserve), and highly available, competitive pressure would ensure that all other sites would need to join in order to avoid a "run on the bank."

If one currency exchange offers voting pool protection, and their biggest competitor refuses, then it would be entirely fair for that exchange's customers to ask, "What do you have to hide? Sites which were not being honest with their customers would not survive long in such an environment.

Although the best possible answer to the problem of third-party theft is to convince all users to handle their own funds themselves, such an outcome is not likely to arrive any time soon. If we must have an ecosystem containing companies who hold bitcoins on behalf of third parties, then we insist upon the best available technology to make this arrangement as secure for those third parties as possible. Right now, that technology is Open-Transactions.

by Justus Ranvier