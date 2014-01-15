---
layout: post
title: "Lex Cryptographia"
description: ""
category: "smart contracts"
tags: ["Justus Ranvier"]
---
{% include JB/setup %}


# Introduction

## The Past

In the [eleventh and twelfth centuries](http://mises.org/daily/2542#4), increases in agricultural production and urbanization led to a new rise of a new professional merchant class who traded within and among towns and kingdoms. Customary law by this time had grown localized, so the merchants needed a universal body of law in order for trade to function on inter-regional levels. This began with a recognition of common customs that already existed, and from there merchants began experimenting with their own contract law, where contracts themselves were the source of law. Because contracts require voluntary entry, objectivity and impartial recognition and enforcement of the law was expected by anyone entering. Merchants would only voluntarily take part in a legal system that treated them fairly. Over time, these voluntary and experimental contractual agreements grew into a universal body of law known as *lex mercatoria* or the “Law Merchant.”

*Lex mercatoria* required no intervening rulers to dictate the law, and in fact its statelessness was the key feature that allowed it to flourish and benefit merchants who sought peaceful inter-regional trade. Indeed, merchants preferred their own court systems recognizing *lex mercatoria* over royal courts. Royal courts would often refuse to see cases involving contracts made in foreign countries. They would refuse to recognize interest agreements on charges of usury. They would refuse to use accounting books as evidence, despite them being central to merchant cases. They were unable to handle technical cases. They were slow and bureaucratic. On the other hand, merchant courts recognized a universal law that could apply to everyone, so geography was not an issue. They recognized voluntary contracts given they held up to community standards. They understood what mattered for cases and could compete in niches that required technical knowledge. They favored expedience and informality so that merchants could get back to business. Instead of physical punishment, merchants could use social incentives such as ostracization. By the thirteenth century, *lex mercatoria* was a body of law universally recognized by merchants and proved that commercial law can develop outside of the state apparatus and perhaps it should remain there.

<!--more-->

## The Present

During the last 30 years, programmers around the world have constructed the foundation of an entirely new economy piece by piece. The popularization of email and the world wide web in the 1990s makes it possible for instant, frictionless communication between individuals located anywhere in the world without regard for national borders. Mobile technology has allowed this access to reach into the most distant and poorest parts of the world. Bitcoin has, for the first time, made instant, frictionless payments possible between individuals located anywhere in the world, without regard for national borders.

We now have all the necessary tools to build a new borderless economy where producers of digital deliverables and their customers can interact directly, without friction or prior restraint, or regard for physical location… almost. There’s still a missing piece that is drastically holding back the genesis of this economy.

We can make agreements online, and make payments when a deal is completed successfully, but when a deal doesn’t work out to the satisfaction of all parties, our options for resolving the conflict in a satisfactory manner are limited.

As anyone who has been paying attention is keenly aware, [fraud](http://www.fraudguides.com/internet-craigslist-scams.asp) and [theft](https://www.paypal.com/us/cgi-bin/webscr?cmd=xpt/Help/general/TopQuestion4-outside) are a [common ](http://www.scambusters.org/ebayscams.html)occurence online, not just in [Bitcoin](https://bitcointalk.org/index.php?topic=83794). The [losses](http://blog.credit.com/2007/06/credit_card_ind/) these scams create is obvious, but as a 19th century writer informed us, “There is only one difference between a bad economist and a good one: the bad economist confines himself to the *visible* effect; the good economist takes into account both the effect that can be seen and those effects that must be *foreseen*.”

What we don’t notice as we look around the the current state of the digital economy is the enormous number of potential transactions that *never happen at all*, because the risk of an unsuccessful trade is so high that the parties who might complete a successful deal never even make the attempt.

## The Future

In order for us to achieve the goal of a borderless, global, digital marketplace we must make it possible for any two (or more) people to trade with the assurance that their deal is likely to conclude successfully. Because our problem set includes people from anywhere in the world, we can’t rely on government-provided legal recourse systems because they are frequently incompatible, expensive, inaccessible, and/or otherwise non-existent.

Since this problem has not yet been solved, we must assume that the existing attempts to do so have been unsuccessful or incomplete. However, in order to design a solution we should look at what has already been tried.

# Background Information

## Reputation systems

Reputation systems are used by services such as Ebay and LocalBitcoins to assist customers in avoid unscrupulous traders, and by giving honest traders an incentive to resolve problems to preserve their feedback rating.

Reputation systems are vulnerable to attacks by malicious traders such as the [Sybil attack](https://en.wikipedia.org/wiki/Sybil_attack) where the attackers create numerous fake profiles to give them false positive ratings, or the [long con](https://en.wikipedia.org/wiki/Long_con), where a trader builds up a good reputation in order to be trusted with increasing value until they reach a threshold wherein it is profitable for them to steal what they’ve been entrusted and abandon their accumulated reputation.

## Payment escrow

Payment escrow is another technique commonly used in online markets. It works by having a trusted third party accept the payment from the buyer and wait to release it to the seller until both parties report a successful transaction. Escrow provides the seller the necessary assurance of being paid so that he can safely release the product, and provides the buyer the assurance of not being required to pay if the product is not received.

Escrow systems are vulnerable to malicious agents colluding with one of the parties or, depending on the protocol involved, &nbsp;outright stealing the payment.

## Surety bonds

[Surety bonds](https://en.wikipedia.org/wiki/Surety_bond) are not typically seen in online markets. They are an ancient concept, with the earliest known examples dating back to Mesopotamian civilizations, and survive in the present day mostly in the blue-collar trades.

A surety bond is money that is placed in escrow as a form of collateral against failure to perform on a contract, or against damages that might be incurred.

For example, in some jurisdictions a plumber might be required to post a $250,000 bond in order to obtain a licence to work. The money is held by a government agency and is used to pay out restitution to customers in the event an error on the plumber‘s part causes significant damage beyond the amount he was paid for a job.

Surety bonds can be thought of a general solution to the problem of contract enforcement, of which payment escrows are a specialized and limited type. An escrow is a special type of surety bond offered by the buyer to the seller which also doubles as the payment. However as the previous example shows, surety bonds can be more general than that. They do not need to be limited to the amount of the payment, and can be offered by potentially all parties in the transaction.

They have the same failure case as payment escrows: the trusted party holding the bond could collude with one party or steal funds.


## Smart Contracts

Smart contracts are agreements between two or more entities where at least some of the terms are specified in, and acted out by, software.

A pure smart contract is entirely software based - with no terms that involve human interpretation and requiring no human action to complete.

A hybrid smart contract is a mixture of software and human-readable language. Some parts of the contract are acted out by software while other parts require human interaction to complete.

## Dispute Prevention and Resolution using Smart Contracts

### Intrinsically cheat-proof contracts

The best way to resolve a dispute is for it to make it impossible to happen in the first place. Doing this means creating some kind of cryptographic protocol which is completely secure against cheating.

One example of this is [atomic cross-blockchain trades](https://en.bitcoin.it/wiki/Atomic_cross-chain_trading). Two parties agree to exchange one cryptocurrency for another, and the transaction is done in such a way that neither side can execute their portion of the trade without releasing funds to the other party. The trade either happens in its entirety, or not at all, which means nobody can walk away empty-handed. The worse possible outcome is that no trade occurs at all and everybody keeps what they had.

Another example is [rapidly-adjusted micropayments](https://bitcointalk.org/index.php?topic=66521). These work by creating a transaction where the customer sends a certain amount of money to the provider of a metered service, and the provider sends the exact same amount back to the customer, and the transaction is not valid until some point in the future.

Between the time when the transaction is created and the time it enters the blockchain, both sides sign continual updates to it - it’s adjusted to make the provider a net recipient of funds as they provide contine services. This protocol is immune to cheating because the customer can immediately cease to sign updated transactions if the provider stops delivering service, and the provider can immediately cut off service if the customer refuses to pay.

### Oracles

Another way to make a dispute-proof smart contract is to use external trustworthy sources ([oracles](https://en.bitcoin.it/wiki/Contracts#Example_4:_Using_external_state)) to provide the necessary state such that the software making up the contract can automatically and unambiguously choose the correct course of action.

### Human Intervention

The last category of dispute is the one most difficult to deal with. Most programmers would rather deal with the previous categories, because they are solvable entirely in software and thus are immune from the complexity and unpredictability of the human condition.

Unfortunately, however, not all contracts can be reduced to pure smart contract form. As long as we want to interact with each other as fellow human beings, we will create agreements which have failure modes that can not be resolved via software. In fact, these might even be the most common of all type of disputes.

Lex Cryptographia is a comprehensive plan to tackle this category of disputes in a low trust, borderless, and decentralized peer to peer manner. With this plan in place the digital economy will be able to achieve its full potential, freed from the uncertainty that arises when the potential exists for disputes in a transaction, but there exists no effective method of resolution or restitution.

# The Solution

## Contract Insurance

Suppose there exists a global, decentralized marketplace where anyone can list offers for any product or service, like a super-Craigslist or EBay. Instead of plain texts listings, however, buyers and sellers post smart contracts. The smart contracts encode all the relevant conditions and payment details, so the marketplace itself only serves to match buyers and sellers, while the smart contract platform handles everything else directly between the participants.

It is in this environment where Lex Cryptographia will operate. The smart contract platform it will operate on is [Open Transactions](https://github.com/FellowTraveler/Open-Transactions/wiki) (OT). The marketplace is a forthcoming feature of OT called the Bazaar. More on OT and why we chose this platform later.

Our proposal is to add a special type of contract to OT that we call an “insurance subcontract”. These are smart contracts defined in a particular way that allow participants in a contract to self-insure their future performance by posting a surety bond. The bond automatically returns to the person who posted it if the main contract is completed successfully. If another party in the main contract issues a dispute message, then control over the bond is handed over to a third party arbitration company for resolution.

This basic structure can be built upon to solve entire categories of dispute and trust problems, but it may not be apparently clear yet. Some examples are in order.

Imagine you have a need for bespoke artwork, perhaps to include on invitations for your upcoming wedding. Artwork is a digital deliverable, so in an ideal case you should be able to choose from artists located all over the globe to obtain the highest quality at the best price available.

As things stand now, however, a resident of Canada is not likely to hire an artist from Nigeria, even if that artist would be the best provider, and the artist is unlikely to accept a Canadian customer. There is a mutual trust problem that prevents both sides from entering into this deal:

*   When you as a customer hire an artist for a time-sensitive job, you are taking a risk that the job will be completed in a satisfactory manner by the deadline. If the artist misses the deadline then you can always just refuse to pay, but now you’re stuck trying to hire someone else to do the work as a rush job (higher price).

*   The artist obviously needs to trust that the customer will pay as agreed after receiving the product.

Using bitcoins as a payment method with escrow is a partial solution to this problem - it addresses the artist’s trust issue - but does nothing to help the customer’s risk.

This is where Lex Cryptographia comes in.


The customer and the artist meet up in the Bazaar and form a hybrid smart contract. The human-readable portion of the contract specifies what kind of art the customer wants, what format it should be delivered in, and when it will be finished.

The software portion of the contract specifies that the customer will pay the amount the artist specified (for this example, $50) upon mutually verified completion.

In addition both people want their counterparty to provide insurance, so both sides also create insurance subcontracts.

The customer’s insurance contract is valued at $50 (the amount of the sale). If the customer fails to pay the invoice when the terms for payment have been met, the artist can invoke the dispute mechanism and ask the customer’s arbitration company to release the bond.

Calculating the value of the artist’s insurance contract is less straightforward. The customer knows she will lose a certain amount of money in terms of hiring a replacement artist at a higher cost if this artist fails to deliver a suitable product by the deadline. She and the artist will negotiate an bond amount that reflects this risk, which could be higher or lower than the sale price. Suppose they arrive at a value of $100.

Now both sides of this deal are protected. If anything goes wrong, both people have recourse to third-party arbitration where the funds needed to pay damages have already been provably sequestered in the insurance contracts at the beginning of the deal.


In the previous example, it’s not obvious why they payer would use a bond instead of just placing the payment itself in escrow. The reason for separating the bond from the payment is that the insurance structure can even handle cases where there is no currency payment at all.

Suppose a carpenter and a dentist are going to barter services by building a deck in exchange for filling a cavity. Even though no currency is changing hands, they might decide to protect themselves by asking the other party to insure their performance in case of some kind of mishap. Because this framework is designed to help people enter contracts across jurisdictional boundaries the bond encapsulates all forms of redress which might be required, of which non-payment is only one.

Besides removing barriers to trade based on lack of trust, certainty, or the ability to collect damages, Lex Cryptographia also greatly diminishes the need for identity and reputation (two things which are problematic to establish and check anyway). Our example Canadian customer doesn’t need to know who the artist is, or what kind of reputation he has. Both people might even be completely anonymous. All they need to know is that they are both protected financially in the event that something goes wrong via a process that is completely independent of spatial location or legal jurisdiction, and which can handle disputes which can be automatically resolved via software as well as disputes which can only be resolved by human intervention.


Every trade that is never even attempted because of uncertainties and mutual incompatibilities between government law systems is a hidden economic loss that affects people all over the world. Giving them the tools to bridge that gap will unlock this potential for the benefit of everyone involved.

## Arbitration


In order for the insurance contracts to function, participants need access to a robust market for arbitration providers. Since the only requirement needed to arbitrate is a willingness to listen to two sides of a disagreement and make a decision, the same software that we’ll use to create smart contracts will also allow users to form arbitration companies. To encourage as many entrants into the market as possible it should be as easy to start one of the companies as it is to open a Facebook account.

One or more individuals will use the incorporation features of OT to form their company. They’ll select the number of members, the amount of consensus needed to make a decision, what types of legal theories they will advertise (Common Law, Sharia, etc), the level of adjudication they will provide, and their rates. All of this information will be broadcast into the same distributed marketplace where other companies and individuals advertise their services, and will be structured so that search engines can quickly locate suitable companies for any given smart contract.

An arbitration company can offer casual services in which they make snap decisions after receiving an email from both sides, or they could offer a lengthy and detailed trial process, or anything in between. The effect of this is to create a market for à la carte law where the customers choose exactly the amount of protection that meets their needs and budget.

One thing that is different about these arbitration companies as compared to other businesses in the ecosystem is that reputation is extremely important for them. Everybody else can use bonds in lieu of relying on reputation in order to create assurance for their customers, but arbitration companies are the linchpin this system relies on in order to function. Fortunately, it’s easier to measure the reliability of an arbitration company in objective manner, so reputation systems are both more accurate and more useful in their case.

### Arbitration Quality Control


Insurance contracts will be structured in such a way that arbitration companies are limited in what they can do - if and only if someone issues a dispute will they be involved, and then they can only divide up the bond between the parties. They won’t be able to keep or divert funds. This means there are only two failure cases: they fail to render a verdict when activated, or they collude with the insured party to render a bad judgement.

A history of exhibiting any of these failure cases can be easily detected by reputation services. Such services could collect highly-relevant data and score arbitration companies via several metrics.


Responsiveness can be scored as the average and median amount of time they take to render a judgement as compared to what they advertise.

As the amount of judgements increases, it will provide a data set which can be used to detect bias. Does an arbitration company rule in favor of its own client more frequently than the industry standard? If so, this is easily detected in addition to other biases.

When arbitration is activated, the arbiter will have the authority to act unilaterally but can optionally request the assent of both parties by having them digitally sign the judgement. This will provide another data set which can be used to judge quality: the best possible outcome would be for an arbitration company to negotiate a settlement that all parties agree to sign. Those outcomes should give a substantial boost to the company’s reputation. Whether it’s better for one party to sign off or for none of them to sign off (in other words, for all parties to be equally dissatisfied) is a question that reputation companies might need to work out empirically.


The special nature of arbitration companies allow for far more objective measurement of their quality, so reputation tracking should be quite capable of separating the good companies from the bad ones.


# Open Transactions


We’ve chosen to implement the Lex Cryptographia project in Open Transactions as opposed to being a stand alone project or directly in Bitcoin. The reason is that at the present time OT is the most feature complete smart contract platform available.


Bitcoin does have opcodes which can be used to process smart contracts in the blockchain, however most of them are currently disabled. Even if they were all enabled, however, the Bitcoin scripting language is stateless and Turing-incomplete, meaning that it is quite restricted in what it can accomplish.

OT uses [ChaiScript](http://www.chaiscript.com/) for smart contracts. It is a full featured programming language which means in theory it is possible to represent any smart contract which is computable (although this flexibility also means special precautions are necessary to prevent execution of pathological scripts). This is most likely overkill for the kinds of smart contracts that most users will want to create, but in order to create a working ecosystem it’s better to have more functionality available than required than not enough.

Our long term stretch goal is to create smart contracts using a restricted subset of OT’s capabilities representing what functionality could plausibly be added to Bitcoin’s scripting language. That opens up the possibility for an upgrade path in which OT-specific transaction servers are no longer required. In that event, OT could become a front end library for creating smart contracts that uses the Bitcoin blockchain for processing. This is the “best of both worlds” outcome in terms of both convenience and security.

# The other 6 billion people


One of the primary goals of Lex Cryptographia is to allow people [outside the developed world](http://www.paymentssource.com/news/a-q-and-a-with-serial-bitcoin-entrepreneur-andreas-antonopoulos-3014626-1.html) to fully participate in the digital economy. By creating a robust contract insurance system that diminishes or eliminates trust issues and the need for reputation, it allows producers in these regions to compete on a more level playing field with producers in more developed areas.

They are still at a disadvantage, however, in that producers in the developed world will on average have more savings which they can use to post as bonds. To insure one’s contracts in order to land income-generating deals, one must first have saved income to post as the bond. While this might at first glance appear to be an insurmountable barrier, there are several ways it can be overcome:

1.  **Price differentiation**: Producers with no savings can still advertise in the Bazaar, but will need to discount their prices to overcome their lack of insurability. They’ll be able to sell to the most price-sensitive customers who are willing to take on additional risk in exchange for a lower cost.

2.  **Traditional insurance**: Standard form insurance contracts will not be sensitive to the source of the bonds. All previous examples have assumed that the insurees are self-insuring by posting their own bond, however it’s equally possible that the arbitration company posts the bonds. In this case they would perform actuarial calculations and collect premiums like a traditional insurance company.

3.  **Microlending**: Similar to the previous method, charities could form for the explicit purpose of helping producers of digital deliverables get a foothold in the marketplace by insuring their first few contracts, until they’ve earned enough to self-insure.

Regardless of the method they use to get started, producers will benefit greatly by retaining profits and using them to insure increasingly larger deals as their experience and success accumulates. Older readers may remember a time before the central banks of the world declared war on savers and recognize this process as “capital formation”.

For those who can not remember that era, think of it as starting out as a [level 1 entrepreneur](http://bitcoinism.blogspot.com/2013/11/censorship-resistant-business-models.html#game) and level grinding until you can take on the more powerful mobs.


# Conclusion


Lex Cryptographia is a plan for addressing trust and recourse problems in online commerce in a way that does not depend on unreliable, inaccessible, non-existent, or contradictory government law systems. By combining the concepts of insurance, surety, smart contracts, and third party arbitration where necessary, it is possible to greatly reduce the risk of non-performance.

Although this is applicable to many types of commerce, we’re going to focus on software tools to help two specific groups:

1.  Producers of digital deliverables who live in the developed world. Smart contract software tools which incorporate Lex Cryptographia can help these people become location-independent while developing a global customer base.

2.  Potential producers of digital deliverables who live in the developing countries and who otherwise have little income opportunity. The ability to insure contracts will help to level the playing field for them in terms of gaining access to international markets.

With this system in place, the digital economy will finally be in a position to achieve its full potential, by providing a method for contract enforcement that is as borderless and decentralized as Bitcoin itself.

by Justus Ranvier