---
title: The Great Bitcoin Scaling Debate-A Timeline
metaDescription: test
date: 2017-12-03T00:00:00.000Z
author: Daniel Morgan
summary: This timeline chronicles the repeated attempts to scale Bitcoin’s blockchain, and details how each attempt has — so far — been unsuccessful. It covers all important dates in the scaling debate, focusing on how and why alternative implementations of Bitcoin have sprung up in an effort to scale the blockchain to a larger block sizes.
tags:
  - bitcoin
---


**Why have so many attempts to scale Bitcoin’s blockchain failed?**

This timeline chronicles the repeated attempts to scale Bitcoin’s blockchain, and details how each attempt has — so far — been unsuccessful. It covers all important dates in the scaling debate, focusing on how and why alternative implementations of Bitcoin have sprung up in an effort to scale the blockchain to a larger block sizes.
 
**A brief overview of why the block size of 1 MB has never increased:**

Efforts to increase the block size of Bitcoin began with appeals from developers like Gavin Andresen, Jeff Garzik, and Mike Hearn as early as 2011. They anticipated a time when the rate of transactions would exceed the available space in blocks and sought to increase the block size limit — a change that might seem straightforward. The block size was put in place to limit the possibility that someone could cheaply spam the network. Sending a large number of transactions was cheap, and it would have been possible to crowd out other transactions [for a small investment](http://gavinandresen.ninja/One-Dollar-Lulz).

The spam control mechanism persists in the form of the block size limit of 1 MB, which in turn limits the transactions per second on the network to about three. While every effort to scale Bitcoin has so far failed for a variety of reasons, what they were seeking to accomplish is still a problem that needs fixing. Developers working on Bitcoin’s main Github repository agree that a block size increase needs to happen, but they have not yet established a way to do this with broad consensus. And they seem to have given up trying for a hard fork block size increase, working towards off-chain solutions that do not require the building of network-wide consensus.

The most recent attempt to increase the base block size of Bitcoin took the form of Segwit2x, which was intended to follow from the introduction of Segregated Witness (Segwit) with a doubling of the block size limit. Segwit2x, and other block size attempts before it, fail because the culture, technology, and governing development team is resistant to what has been deemed ‘contentious.’ A ‘contentious’ proposal is something that doesn’t yet have complete support from the Bitcoin community. Bitcoin Classic, Bitcoin XT, Bitcoin Unlimited and Segwit2x are all examples of alternative clients that have sought to build a consensus in larger block sizes.

My hope is that this timeline provides insight into this long-running debate. The moments I’ve pulled from the block size debate provide an on-the-ground view of how block size proposals are born, and how different actors in the Bitcoin community respond to the proposals. While some groups welcome simple block size increases, others label these attempts as risky, dangerous, or even an ‘attack on Bitcoin itself’. As you read this timeline, please keep in mind that it’s not intended to be comprehensive, and I’m not intending to come off as completely unbiased. If I left out my personal understanding of the scaling debates and how I understood these arguments *at the time,* I would be leaving out the most interesting part of Bitcoin to me: the social layer on top of the math. That’s what draws me to Bitcoin. On one hand there are a set of rules defined by algorithms and raw hashpower; on the other, social and economic values govern how individuals respond to threats and perceived attacks.

To create this timeline, I’ve pulled from developer mailing lists, blog posts from developers, the Chinese bitcoin community, and additional vetted sources from around the net. I’ve tried to highlight pivotal moments only, and have included petty drama only when it’s appropriate for telling the complete story.

I think it’s important to also start with a quote from Paul Sztorc from his blog post “[Salvaging the Blocksize Debate](http://www.truthcoin.info/blog/blocksize-conversation/)”

> My only purpose here, is to comfort those who are frustrated. I hope to explain *why* the blocksize conversation is so horrible, and help move it forward. If you aren’t interested in that, now’s the time to navigate elsewhere.

**Let’s start.**

**2009 — April**

In a discussion on the Block size on [Bitcointalk](https://bitcointalk.org/index.php?topic=149668.msg1596879#msg1596879), Mike Hearn shares an early email he received from Satoshi Nakamoto in response to his question about the block size limit:

[![](https://cdn-images-1.medium.com/max/1600/1*z33VDWumRyubW-L9SIGYeg.png)](https://bitcointalk.org/index.php?topic=149668.msg1596879#msg1596879)

https://bitcointalk.org/index.php?topic=149668.msg1596879#msg1596879

It is important to understand that much has changed since Satoshi Nakamoto departed Bitcoin, but claiming that Satoshi meant the 1 MB block size (or any) limit to persist irrespective of the rising speed of computers is incorrect.

**2010–7–14**

A `max_block_size` value of 1MB [set on the client](https://github.com/bitcoin/bitcoin/commit/a30b56ebe76ffff9f9cc8a6667186179413c6349#diff-118fcbaaba162ba17933c7893247df3aR2614). ([View snapshot on Sourceforge](https://sourceforge.net/p/bitcoin/code/103/log/?path=)).

**2010–10–24**

**After some discussion,** [Hal Finney, Satoshi (Bitcoin’s creator), and the user ‘Cryddit’ on Bitcointalk](https://bitcointalk.org/index.php?topic=946236.msg10388435#msg10388435) imposed a 1MB default block size to reduce the chance of spam transactions hijacking blockspace, or the possibility of cheap DoS attacks. Cryddit below explains why this limit was put in place:

![](https://cdn-images-1.medium.com/max/1600/0*idtiYHVvXJERF21r.)

via[ https://bitcointalk.org/index.php?topic=946236.msg10388435#msg10388435](https://bitcointalk.org/index.php?topic=946236.msg10388435#msg10388435)

Since transactions could be included without fees, transactions (which could also represent data piggybacking in a tiny transaction) may result in a permanent and expensive data store outside of the goals for the network. Recently, Vitalik Buterin, the creator of Ethereum, claimed that this limit is what encouraged him to develop an alternative system instead of piggybacking on Bitcoin or Mastercoin.

When asked about how this limit would be removed in the future, Satoshi wrote:

> It can be phased in, like:

*if (blocknumber > 115000)*

*maxblocksize = largerlimit*

> It can start being in versions way ahead, so by the time it reaches that block number and goes into effect, the older versions that don’t have it are already obsolete.

> When we’re near the cutoff block number, I can put an alert to old versions to make sure they know they have to upgrade.

If you look into the technical mechanism by which the block size is actually limited, you’ll likely encounter [the above conversation](https://bitcointalk.org/index.php?topic=1347.msg15366#msg15366) where Satoshi recommends a future date for setting a block size increase. It’s important to note that it’s a bit more complicated than that one line. Garzik, a developer who at that time had worked closely on the Bitcoin code, proposed (perhaps in a provocative way) increasing the block limit to allow a huge number of additional transactions per second to match Paypal / Visa volume, but Satoshi recommended an upgrade that kicks in down the road.

What many forget is that this conversation is sandwiched between posts by Garzik, the developer of the[ BTC1](https://github.com/btc1/bitcoin) / [Segwit2x](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77) implementation. Had Garzik stuck to his guns and worked towards implementing a gradual, sensible increase in 2010, we would have no Bitcoin Cash, Bitcoin Classic, Bitcoin Unlimited, or the implementation he worked on, Segwit2x. You’ll encounter these implementations further down this timeline.

![](https://cdn-images-1.medium.com/max/1600/0*T08FSu5vyyfCeqEA.)

Greg had his own problems with whole-network upgrades.

**2011–6–14**

Gavin Andresen presented Bitcoin to the CIA, which may have precipitated Bitcoin’s creator, Satoshi Nakamoto, going dark. As you can imagine, the Bitcoin community is a suspicious bunch. Without Satoshi, the block size limit has no authoritative decision-maker. The network of miners, users, and developers at this time was extremely small.

**2012–7–12**

Andresen [set a block size limit of 250](https://github.com/bitcoin/bitcoin/commit/c555400ca134991e39d5e3a565fcd2215abe56f6#diff-c865a8939105e6350a50af02766291b7R284) KB.

**2013–11–7**

Andresen’s first commit to the repository was in [July of 2010](https://github.com/bitcoin/bitcoin/commit/8bd66202c324a6c7a79abc0f1f0558dacbc59460), and he had admin access to the official repository for Bitcoin after working closely with Satoshi Nakamoto to improve Bitcoin in the early days. He [set the block size to 750](https://github.com/bitcoin/bitcoin/commit/ad898b40aaf06c1cc7ac12e953805720fc9217c0#diff-e8db9b851adc2422aadfffca88f14c91R39) KB on this day. Note that at this time there was only one group that worked on the Bitcoin repository, and there was no notion of a ‘Core developer’ since there were no other implementations, or need for designating a ‘team’ working on the network. The idea of a Core Developer sprang up partially in response to Bitcoin Classic (an alternative and popular client you’ll read about later), which Andresen launched after leaving the core crew of developers.

**2014–4–7**

Andresen stepped down as main developer and release manager of Bitcoin.

**2014–6–10**

Mike Hearn published a *Bitcoin Improvement Proposal* (BIP 64), which started the basis of his alternative client Bitcoin XT. It was built to more easily link with his crowdfunding project called [‘Lighthouse’](https://techcrunch.com/2014/05/23/lighthouse-is-a-crowdfunding-platform-built-on-top-of-bitcoin/). In December of this year, Hearn released version .1 of Bitcoin XT. [Here’s an intro from Mike about why Bitcoin XT was created](https://www.youtube.com/watch?v=8JmvkyQyD8w&t=47m58s).

Bitcoin XT would later include Andresen’s[ BIP 101](https://github.com/bitcoin/bips/blob/master/bip-0101.mediawiki) proposal, which raised the block size to 8MB. Bitcoin XT arrived on the scene before Bitcoin Classic, but set the stage for what a block size limit initiated by a hard fork looks like. Unfortunately, the block size increase was attacked as too risky by the core development team.

**2014–9–25**

Blocks get closer to the ‘full state’, with an average block size of around 800k.

**2014–10–14**

Ittay Eyal, Adem Efe Gencer, Emin Gun Sirer, and Robbert van Reness introduce Bitcoin-NG, a method of scaling Bitcoin’s capacity by offloading transactions under the same security model:

http://hackingdistributed.com/2015/10/14/bitcoin-ng/

[![](https://cdn-images-1.medium.com/max/1600/1*OIiRkb9FCL1nmXcDvi61zg.png)](https://arxiv.org/pdf/1510.02037.pdf)

via: https://arxiv.org/pdf/1510.02037.pdf

**2015–03–28**

Mike Hearn wrote one of the first alternative client implementations of Bitcoin (Bitcoinj), and wrote a post titled [Replace by Fee](https://medium.com/@octskyward/replace-by-fee-43edd9a1dd6d) specifically about crutches built into Bitcoin that make a ‘fee market’ more navigable by wallet software while avoiding the core block space problem:

> I think RBF is a badly thought out idea that won’t work, doesn’t do what it’s claimed to do and would be harmful for Bitcoin if adopted.

Replace by Fee (RBF), aka ‘Fee Bumping’ or ‘Transaction Replacement’ was added to Bitcoin as an attempt to make unpredictable transaction fees (and blocks increasingly becoming full) something that wallets can program around. It eliminated the possibility for a low fee transaction to become stuck but opened up the network to double spending:

> The idea behind “scorched earth” is that if someone buys something with an unconfirmed transaction, when they walk out of the shop and press undo they double spend the original output to themselves with a higher fee, but the merchant sees this and then adds a spend-to-self transaction on top of their original payment with a slightly higher fee, and then the fraudsters wallet does the same to bump the fee on *his* chain of transactions, and so on and so on until the entire payment has been consumed in fees. The fraudster gets the goods, the payment is now going to a miner instead of the merchant, and the merchant is left with nothing.

Another note on the insanity of allowing a fee market to develop comes from [this post](http://hackingdistributed.com/2015/12/23/bitcoin-fee-market/) by Emin Gün Sirer posted a few months later on 12/23/2015:

> What is not a good argument is that “we don’t have experience with what will happen when the fee market develops, and it will have to develop eventually, so let’s hasten the day.” I do not have experience with my old age. I do not go around artificially inducing osteoporosis to get ready for my old days — instead, I make the best of my working days when I’m blessed to have a working skeleton.

View [usage of RBF here](https://p2sh.info/dashboard/db/replace-by-fee?orgId=1).

**2015–05–04**

Andresen argued that the block size limit should be addressed as soon as possible. At the time, blocks were 30–40% full.

*If the number of transactions waiting gets large enough, the end result will be an over-saturated network, busy doing nothing productive. I don’t think that is likely– it is more likely people just stop using Bitcoin because transaction confirmation becomes increasingly unreliable.*

[ **Why increasing the max block size is urgent by Gavin Andresen** ](http://gavinandresen.ninja/why-increasing-the-max-block-size-is-urgent)

**2015–05–30**

Censorship is an important topic for Bitcoiners. The flow of information about the market, the development team, and the entire universe of a digital currency first flows through a small number of digital platforms such as[ BitcoinTalk](https://bitcointalk.org) (this was the first) and[ Reddit](http://reddit.com/r/bitcoin). Here is the kind of post from 2015 that would get a user banned today, in 2017: the Reddit user *usemein* asked “[ *Is the Blockstream company the reason why 4 core developers won’t increase the blocksize* ](https://www.reddit.com/r/Bitcoin/comments/37vg8y/istheblockstreamcompanythereasonwhy4core/)?”

If you continue reading below, you’ll see a few more references to this company, as well as a thorough piece on censorship. If you’ve already taken a dip in the uncensored stream of Bitcoin information, you’ve already heard of Blockstream’s legacy. Many of the claims against Blockstream are wild conspiratorial claims and typically don’t hold up under scrutiny, but knowing that their business model depends on a constrained block size has focused a great deal of suspicion on their employees who work on Bitcoin’s development.

**2015–06–4**

Andresen rejected the idea that developers should set an explicit and unchangeable limit on block size, saying it was a ‘policy decision’, and that developers should instead allow nodes and miners to decide for themselves:

![](https://cdn-images-1.medium.com/max/1600/0*AoLjWLLH2Nm3gLsU.)

via:[ https://github.com/bitcoin/bitcoin/pull/6231#issuecomment-108892765](https://github.com/bitcoin/bitcoin/pull/6231#issuecomment-108892765)

The goal of some commenters on that pull request, especially Luke DashJr, was to get Bitcoin into a fee market state, where transactions need to compete with one another for block space inclusion. The argument that economic decisions (such as introducing and supporting a fee market) are incompatible with capacity planning decisions — engineering decisions — remains a topic of debate.

**2015–06–8**

47m 58s in, Mike Hearn speaks about the creation of Bitcoin XT in this interview, and elaborates his concept of a Benevolent Dictator for a development team:

**2015–06–12**

![](https://cdn-images-1.medium.com/max/1600/0*RmYRQ3jtGw4JQgJN.)

Chinese miners signed a statement that they want 8MB blocks. Signatories included the large mining companies F2pool, BTCChina, Antpool, Huobi, and BW.

via[ https://medium.com/@zhangsanbtc/why-we-must-oppose-cores-segwit-soft-fork-bitcoin-miner-jiang-zhuo-er-tells-you-why-28f820d51f98](https://medium.com/@zhangsanbtc/why-we-must-oppose-cores-segwit-soft-fork-bitcoin-miner-jiang-zhuo-er-tells-you-why-28f820d51f98)

**2015–06–22**

Bram Cohen, creator of Bittorent who has thrown his weight into the block size debate a couple of times, posted “[Bitcoin’s Ironic Crisis](https://medium.com/@bramcohen/bitcoin-s-ironic-crisis-32226a85e39f)”, in which he made fun anyone preparing for a state where blocks are full of transactions. He called raising the block size limit paternalistic and totalitarian.

> *The proposed ‘solution’ to the ‘problem’ of hitting the transaction rate limit is to raise the limit from 1 megabyte to 20 megabytes. This sort of change flies directly in the face of the ethos of Bitcoin. For things to be left alone and transaction fees left to be determined by market rate is directly in line with the distributed libertarian principles on which Bitcoin was founded. For the limit to be raised in advance to avoid hitting it is paternalistic and totalitarian.*

The idea that the top-down approach to limits (or removing them) is ‘paternalistic’ resurfaced in a March 2017 discussion between Andresen and Matt Corallo (Bitcoin Core Contributor):

[ **Ask a simple question... * Gavin Andresen**
*This is a conversation with Matt Corallo (Bitcoin Core contributor) that started on twitter and migrated into email…* gavinandresen.ninja](http://gavinandresen.ninja/ask-a-simple-question)

**2015–06–24**

BTCChina’s director of engineering Mikael Wang [told CoinTelegraph](https://cointelegraph.com/news/chinese-mining-pools-call-for-consensus-refuse-switch-to-bitcoin-xt):

“We think Gavin’s proposal is a well-balanced solution that we all can stand behind and support. The initial 8 megabyte block size increase was also the agreed number amongst all mining operators in China. BTCChina Pool will unfortunately not be running Bitcoin XT due to its experimental nature, but we are looking forward to see this patch merged into Bitcoin Core.”

Code from an alternative client with a higher block size limit has never been merged into Bitcoin Core, no matter the community support. While the block size debate could have effectively ended after merging this code as Mikael Wang suggests, this is something Bitcoin Core would never do.

**2015–06–30**

To address denial of service attacks, Hearn blocked Tor exit nodes in his Bitcoin XT implementation:[ https://github.com/bitcoinxt/bitcoinxt/commit/73c9efe74c5cc8faea9c2b2c785a2f5b68aa4c23](https://github.com/bitcoinxt/bitcoinxt/commit/73c9efe74c5cc8faea9c2b2c785a2f5b68aa4c23)

Because the idea of censoring anyone’s connection to the Bitcoin network is tantamount to treason, this did not go over well, and may have sealed the fate of the XT project. It quickly began losing support from the community.

**2015–08–02**

LiteCoinGuy posted “[ **Why i will support bigger blocks — and you should too** ](https://bitcointalk.org/index.php?topic=1141086.0) **”** on BitcoinTalk compiling support for larger blocks. The post included a chart detailing Core developers’ support, with Blockstream employees squarely in the 1MB camp:

![](https://cdn-images-1.medium.com/max/1600/0*fQGXc7QWstApG1Kp.)

**2015–08–12**

Here’s an excerpt from a discussion about soft vs. hard forks by Hearn:

*It’s worth noting that Satoshi did not use the phrase “hard fork”; presumably the notion that any other kind of fork might exist didn’t occur to him. The idea of a soft fork wasn’t around back then, and rightly so, as the concept is itself deeply flawed: in a correctly functioning Bitcoin network no soft forks should ever happen.*

Hard forks signal a network-wide upgrade, similar to typical software development cycles. Soft forks are a tightening of rules that do not require network-wide collaboration or complete consensus.

[ **On consensus and forks**
*What is the difference between a hard and soft fork?* medium.com](https://medium.com/@octskyward/on-consensus-and-forks-c6a050c792e7)

An important distinction: soft forks make the rules of Bitcoin more strict but do not create incompatible, non-upgraded clients. Hard forks require all clients to upgrade due to a loosening of rules.

**2015–08–15**

Hearn published “Why is Bitcoin Forking”

[ **Why is Bitcoin forking?** ](https://medium.com/faith-and-future/why-is-bitcoin-forking-d647312d22c1)

[ *A tale of differing visions* medium.com](https://medium.com/faith-and-future/why-is-bitcoin-forking-d647312d22c1)

In this post he explained his XT project and his vision for Bitcoin (scaling to Visa levels of transactions per second), as well as called out the Lightning network as a departure from Bitcoin. The Lightning network is a protocol that is commonly touted as the solution to Bitcoin’s scaling problem:

*The so-called “Lightning network” that is being pushed as an alternative to Satoshi’s design does not exist. The* [ *paper describing it* ](https://lightning.network/lightning-network-paper-DRAFT-0.5.pdf) *was only published earlier this year. If implemented, it would represent a vast departure from the Bitcoin we all know and love. To pick just one difference amongst many, Bitcoin addresses wouldn’t work. What they’d be replaced with has not been worked out (because nobody knows). There are many other surprising gotchas, which I* [ *published an article about* ](https://medium.com/@octskyward/the-capacity-cliff-586d1bf7715e) *. It’s deeply unclear that whatever is finally produced would be better than the Bitcoin we have now.*

Also on this day, Morgan E. Peck conducted an excellent interview with Adam Back with the sensationalist title “Adam Back Says the Bitcoin Fork Is a Coup” in *IEEE Spectrum.* After some back and forth about the legitimacy of Bitcoin XT where Back claimed that XT sought consensus the wrong way, Peck asks *:*

> In a way though, BitcoinXT is also an avenue toward consensus. Hearn claims that Bitcoin’s core development team has reached gridlock and says he’s forcing a vote that would otherwise never take place. So, what’s wrong with that?

… Back replied:

> The timing was exceedingly odd. In the past they might’ve said progress was slow, but they did this after two months of active progress. We were rather hoping in the circumstances that they would be collaborative and work in the process with everyone else. It seems like they were irritated that their proposal was not automatically winning.

> In a way it’s less the details of the proposal and more the attempt to bypass the scientific review process and impose one design by lobbying, blogging, and populist campaign. I mean, what kind of message does it send. Should everyone else write a web page and go lobby companies? It’s not a constructive way forward and magnifies the risk of the fork failing. If it fails in an uncontrolled way it could be as much fun as a euro exit.

**2015–08–16**

Andresen’s BIP101 proposal merged into the XT codebase. This would have caused a hard fork if the majority of miners had upgraded to this client.

https://github.com/bitcoinxt/bitcoinxt/commit/946e3ba8c7806a66c2b834d3817ff0c986c0811b

**2015–08–17**

In light of the news from August 16 shown above, Theymos, the moderator of r/bitcoin, explained a new policy whereby discussions of hard fork proposals to change the Bitcoin rules (even raising the block size limit) would be considered discussion of ‘altcoins’, aka ‘off topic’. Thus began heavy censorship of any discussion on /r/bitcoin to raise the block size limit through the only mechanism to raise the block size limit: a hard fork. [Theymos](https://www.google.com/search?q=theymos+bitcointalk+forums&oq=theymos+bitcointalk+forums&aqs=chrome..69i57j0.4095j0j7&sourceid=chrome&ie=UTF-8), who is famous for receiving hundreds of thousands of dollars to develop new forums’ software and never releasing anything, explained his decision:

*“* ***Why is XT considered an altcoin even though it hasn’t broken away from Bitcoin yet?***

*Because it is intentionally programmed to diverge from Bitcoin, I don’t consider it to be important that XT is not distinct from Bitcoin quite yet. If someone created a fork of Bitcoin Core that allowed miners to continue mining 25 BTC per block forever, would that be “Bitcoin” even though it doesn’t split from the Bitcoin currency/network quite yet? (I’d say no.)”*

[The full post](https://www.reddit.com/r/bitcoin/comments/3h9cq4/itstimeforabreakabouttherecentmess/).

The phrase: “Because it is intentionally programmed to diverge from Bitcoin” explains the exact mechanism by which hard forks activate: a block date in the future is set where the fork occurs if miners mine blocks following that ruleset. Another phrase for this is “the Nakamoto consensus”, a process by which everyone works in their best interest to create what they believe to be the best set of rules for the network. Without transparency of information and the labelling of hard fork proposals as altcoins, the system breaks down.

An *altcoin* up until that point did not describe a plan to build consensus towards a hard fork requiring miner support. This wordsmithing has become handy by those arguing for small blocks. A hard fork attempt, with efforts to build consensus, also at this time became labelled as a ‘51% attack’, which perverts the same consensus-building framework required to upgrade Bitcoin.

On this day a huge curtain was drawn between Bitcoin users. On one side were those holding onto the status quo, and on the other a growing effort to adapt Bitcoin to the future everyone knew was coming: rising fees and degraded service due to a constrained block space. This accelerated the move to a new Bitcoin subreddit, r/btc.

Average transaction fee: 50 cents.

**2015–08–20**

Adam Back, Blockstream’s CEO who developed one of the key algorithms behind Bitcoin and still works with Core developers, in [an interview](https://www.cnbc.com/2015/08/20/bitcoin-splits-will-it-break-or-be-better-than-ever.html) with Everett Rosenfeld of CNBC, claimed that Bitcoin XT was no good at all, was risky, and that the activation rate was too low (75 percent).

> *But Adam Back, who developed one of the key algorithms behind bitcoin and still works with core developers, said the complaints about XT are manyfold, including worries that a 75 percent activation vote is too low, and that some of the other changes to the program are not sufficiently secure.*

> *Back said the community is actively working on finding solutions (with developer workshops scheduled) to the block size problem, and that jumping ahead of the normal review system is “a little puzzling” and “kind of disappointing.”*

Hearn responded:

> *Mike Hearn, one of the developers behind XT,* [ *wrote in a lengthy post* ](https://medium.com/@octskyward/why-is-bitcoin-forking-d647312d22c1) *explaining the fork that the current limitations of the original software are blocking the growth of bitcoin and its blockchain currency. He disputed Bitcoin.org’s assessment of worst-case scenarios, and said that the fork may be the best way to save the currency from becoming irrelevant.*

**2015–08–25**

[ **Inside the Fight Over Bitcoin's Future**
*A terrific rumpus broke out in the world of Bitcoin last week, when veteran developers Gavin Andresen and Mike Hearn…* www.newyorker.com](https://www.newyorker.com/business/currency/inside-the-fight-over-bitcoins-future)

In response to a recently blocked proposal by Hearn and Andresen for a new direction in the debate over hard forks, Maria Bustillos in The *New Yorker* wrote about this key moment where Core developers could decide on a path forward.

*In the absence of institutions capable of implementing clear standards, it’s plain that Andresen and Hearn decided to take matters into their own hands. XT is above all a path toward establishing new leadership. I asked Andresen whether, if XT were to achieve full acceptance, he would then include all the earlier Bitcoin core devs in the new XT team. He replied that “[XT] will have a different set of developers. Part of the reason for forking is to have a clear decision-making process for the software development.”*

[ *A terrific rumpus broke out in the world of Bitcoin last week, when veteran developers Gavin Andresen and Mike Hearn…* www.newyorker.com](https://www.newyorker.com/business/currency/inside-the-fight-over-bitcoins-future)

All hard fork attempts have risen from the fact that Bitcoin Core has chosen not to work on building consensus for a hard fork that increases the block size. (In fact, the ‘Segwit2x’ hard fork, which was cancelled Nov. 8th, 2017, rose out of the frustration in Core’s inaction.)

Just one day prior to the above article’s publication date, it was announced that major Bitcoin companies had signed their support for Bitcoin XT:[ https://blog.blockchain.com/wp-content/uploads/2015/08/Industry-Block-Size-letter-All-Signed.pdf](https://blog.blockchain.com/wp-content/uploads/2015/08/Industry-Block-Size-letter-All-Signed.pdf)

More support for the Bitcoin XT /[ Bip 109](https://github.com/bitcoin/bips/blob/master/bip-0109.mediawiki) proposal can be found here:[ https://bitcoinxt.software/onboard.html](https://bitcoinxt.software/onboard.html) [[archive](http://archive.is/DKKTC)]

**2015–08–29**

Core developers stepped up DDoS attacks:

[Bitcoin XT nodes continue to be attacked with Distributed Denial of Service (DDoS) attacks](https://www.reddit.com/r/bitcoinxt/comments/3iumsr/udp_flood_ddos_attacks_against_xt_nodes/).

**2015–9–3**

Things started heating up, and attacks against Bitcoin XT hit a fever pitch:[ Bitcoin XT nodes attacked again](https://www.reddit.com/r/Bitcoin/comments/3jj2hf/bitcoin_xt_nodes_being_ddosed/). See more cases of XT nodes being attacked below.

* https://www.reddit.com/r/bitcoinxt/comments/3iumsr/udp_flood_ddos_attacks_against_xt_nodes/
* https://www.reddit.com/r/bitcoinxt/comments/3j28mo/udp_flood_ddos_attacks_part_ii/
* https://www.reddit.com/r/bitcoinxt/comments/3j84lz/help_to_keep_bitcoin_xt_nodes_up_and_protected/
* https://www.reddit.com/r/bitcoinxt/comments/3jg2rt/the_ddoses_are_still_real/
* https://www.reddit.com/r/bitcoinxt/comments/3jemi9/my_node_is_constantly_dosed/
* (For a list of known DDoS attacks against nodes attempting to scale Bitcoin, [visit this page by Derek Makgill](https://wakgill.github.io/deryk/bitcoin-cyber-attacks))

At this time, Hearn was also being relentlessly attacked and character assassinated. One key topic of concern was his statement that he would be the ‘benevolent dictator’ if a disagreement between he and Andresen arose. [This interview](https://www.youtube.com/watch?v=8JmvkyQyD8w) is a great explanation of what was meant by the ‘Benevolent Dictator’ statement, which his opponents used against him.

**2015–09–06**

Bitfury, a leading supplier of Bitcoin Mining rigs (at the time) released a white paper: “Block Size Increase.” After exhaustive analysis of various scaling proposals, the conclusion states:

![](https://cdn-images-1.medium.com/max/1600/0*yhDlW6xTYOmVYlMH.)

[Read the entire paper here](http://bitfury.com/content/5-white-papers-research/block-size-1.1.1.pdf).

**2015–11–02**

Hearn posted commentary on miner voting:

[ **On block sizes** ](https://medium.com/block-chain/on-block-sizes-e047bc9f830)

A key part of Hearn’s post:

![](https://cdn-images-1.medium.com/max/1600/0*-iq-HpxoaHNBR8gu.)

Another excerpt from the article by Hearn on Nov. 2, 2015 concludes with:

*Decentralisation comes not from some nebulous developer process that’s ignored the moment it goes against what Blockstream wants. It comes from people’s ability to be informed and then choose software that matches their beliefs. As it always did.*

**2015–12–07**

With pressure to rally around a blocksize increase mounting, Bitcoin Core Developers posted a set of answers to scaling questions:

http://archive.is/https://bitcoin.org/en/bitcoin-core/capacity-increases-faq

![](https://cdn-images-1.medium.com/max/1600/0*UtebsTI204gjqo-s.)

Their roadmap (shown above) did not include any block size increases, but it did allow (via Segwit) for an increased ‘block weight’ limit. In their estimate of what this would mean for block size they wrote:

> *According to some* [ *calculations* ](http://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-December/011869.html) *performed by Anthony Towns, a block filled with standard single-signature P2PKH transactions would be about 1.6MB and a block filled with 2-of-2 multisignature transactions would be about 2.0MB”*

This ‘blockweight’ change has caused (and really ramped up in November 2017) the call for more Segwit wallet support to take advantage of this block weight value. Fees are slightly lower (sometimes) for Segwit transactions, but adoption has been slow.

Also on this date, a post by Gregory Maxwell hit the Linux Foundation mailing list that Bitcoin Developers use for discussion:

“[[bitcoin-dev] Capacity increases for the Bitcoin system](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-December/011865.html).”

> *Finally — at some point the capacity increases from the above may not be enough. Delivery on relay improvements, segwit fraud proofs, dynamic block size controls, and other advances in technology will reduce the risk and therefore controversy around moderate block size increase proposals (such as 2/4/8 rescaled to respect Segwit’s increase). Bitcoin will be able to move forward with these increases when improvements and understanding render their risks widely acceptable relative to the risks of not deploying them.*

Bitcoin Core signaled that they were considering a 2MB, 4MB or 8MB block size increase around other optimizations. Their work on Segwit, which is technically a block size increase (since it segregates witness data and changes block size to ‘block weight’ with a cap of 4MB) has changed this discussion. After the activation of Segwit in 2017, calls for a blocksize are now answered with ‘Segwit is a Blocksize increase’. [Read this update](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-December/011865.html).

**2015–12–23**

After everyone kept bugging Bitcoin Core about block size increases, they[ posted a massive explanation](http://archive.is/vPFCQ) on how they are addressing approaching scaling without directly increasing the block size.

2015–12–26

Very high-profile support for Bitcoin XT:

This resulted in [the suggestion](http://precipitated) that Coinbase be delisted from the Bitcoin.org ‘Choose your Wallet’ page.

[![](https://cdn-images-1.medium.com/max/1600/1*7gZBVaoGLst02iYdOmfLKQ.png)](https://github.com/bitcoin-dot-org/bitcoin.org/pull/1178#issue-123957573)

Charlie Lee, the creator of Litecoin [chimes in](https://github.com/bitcoin-dot-org/bitcoin.org/pull/1178#issuecomment-167389049). On this day Coinbase only supported Bitcoin and did not allow Ethereum or Litecoin trading.

[![](https://cdn-images-1.medium.com/max/1600/1*gTckr1Ac4AMGqY_2Bym4KQ.png)](https://github.com/bitcoin-dot-org/bitcoin.org/pull/1178#issuecomment-167389049)

“The party line” does not allow discussion of alternative implementations. The Bitcoin.org repository is a key place where new users learn about Bitcoin so this is a big deal.

**2015–12–28**

A question “What is you guy’s opinions on Bitcoin XT and BIP101?” was removed from r/Bitcoin, a signal of more heavy-handed censorship:

![](https://cdn-images-1.medium.com/max/1600/1*MyQLkc5Y6Ydm4HhZ1A3UFA.png)

[via](https://archive.is/35ojq)

**2015–30–2015**

![](https://cdn-images-1.medium.com/max/1600/1*v4TRnvvu5PKR_j2aGekANg.jpeg)

Andreas Antonopoulos here subtly calls out Back on the claim that Segwit will result in a meaningful increase in throughput. Back replies that 2MB is next step. This would amount to Segwit2X, which Back did not support. The 2–4–8 reference is to Greg Maxwell’s [note on the developer mailing list](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2015-December/011865.html) 23 days earlier that a 2MB, 4MB, then 8MB increase makes sense.

**2016–01–13**

/r/bitcoin moderator Theymos got caught hiding posts using CSS rules.

http://archive.is/BMM9P

Also on this date r/bitcoin moderators [censored discussion of Bitcoin Classic](https://www.reddit.com/r/Bitcoin/comments/40ppt9/censored_front_page_thread_about_bitcoin_classic/cyw404f/).

**2016–01–14**

[Hearn quit Bitcoin](https://blog.plan99.net/the-resolution-of-the-bitcoin-experiment-dabb30201f7) and specifically mentioned the stranglehold Bitcoin Core has on block size limit:

***Why has the capacity limit not been raised?*** *Because the block chain is controlled by Chinese miners, just two of whom control more than 50% of the hash power. At a recent conference over 95% of hashing power was controlled by* [ *a handful of guys sitting on a single stage* ](https://pbs.twimg.com/media/CVhkEhtUAAAl0LH.jpg) *. The miners are not allowing the block chain to grow.*

***Why are they not allowing it to grow?*** *Several reasons. One is that the developers of the “Bitcoin Core” software that they run have refused to implement the necessary changes. Another is that the miners refuse to switch to any competing product, as they perceive doing so as “disloyalty” — and they’re terrified of doing anything that might make the news as a “split” and cause investor panic. They have chosen instead to ignore the problem and hope it goes away.*

He continued:

*The resulting civil war has seen Coinbase — the largest and best known Bitcoin startup in the USA —*  [ *be erased from the official Bitcoin website for picking the “wrong” side* ](https://github.com/bitcoin-dot-org/bitcoin.org/pull/1178) *and* [ *banned from the community forums* ](https://www.reddit.com/r/Bitcoin/comments/3rejl9/coinbase_ceo_brian_armstrong_bip_101_is_the_best/cwpglh6) *. When parts of the community are viciously turning on the people that have introduced millions of users to the currency, you know things have got really crazy.*

[ **The resolution of the Bitcoin experiment** ](https://blog.plan99.net/the-resolution-of-the-bitcoin-experiment-dabb30201f7)

[ *I’ve spent more than 5 years being a Bitcoin developer. The software I’ve written has been used by millions of users…* blog.plan99.net](https://blog.plan99.net/the-resolution-of-the-bitcoin-experiment-dabb30201f7)

**2016–2–4**

When Blockstream, who employs several Bitcoin Core developers, attempted to market themselves, they put their Bitcoin protocol governance on the table as an asset:

***The governance of Bitcoin Core*** *, like many other open source projects,* ***is technocratic, where a handful of “core devs” (a dynamic group that includes several Blockstream team-members) deliberate the merits of various changes to the protocol*** *, and decide how to move the puck forward, hoping to convince each other and the wider industry of their consensus.*

The above quote is from:

[ **Our Investment in Blockstream** ](http://www.mosaicventures.com/mosaicblog/2016/2/4/our-investment-in-blockstream)

[ *At a time when sceptics are speculating about the demise of bitcoin the currency, and casting doubt on the viability of…* www.mosaicventures.com](http://www.mosaicventures.com/mosaicblog/2016/2/4/our-investment-in-blockstream)

**2016–01–16**

Bitcoin Classic support hit 49%.

![](https://cdn-images-1.medium.com/max/1600/0*5qVXhZjrlImD5YQo.)

[via](https://www.reddit.com/r/btc/comments/414qxh/49_of_bitcoin_mining_pools_support_bitcoin/cz0ceao/)

**2016–01–17**

Austin Hill, CEO of Blockstream, [claimed that hard forks result in lost funds](https://www.reddit.com/r/btc/comments/41c8n5/as_core_blockstream_collapses_and_classic_gains/).

**2016–1–31**

[Bitcoin XT](https://en.wikipedia.org/wiki/Bitcoin_XT#cite_ref-cdns_13-0) nodes precipitously collapsed:

![](https://cdn-images-1.medium.com/max/1600/0*5BxnS8TwiS6j59cH.)

**2016–1–16**

Greg Maxwell, CTO of Blockstream and contributor to Bitcoin Core developer [posts the following](https://botbot.me/freenode/bitcoin-wizards/2016-01-17/?msg=58099943&page=1) in response to a question about fee pressure in the #bitcoin-wizards IRC channel:

> Greg: <em>There is nothing wrong with full blocks, and blocks have been “full” relative to what miners would produce for _years_. Full blocks is the natural state of the system: The demand for externalized-cost highly replicated external storage at price zero is effectively infinite.</em>
> bsm117532: <em>Are you arguing “fee pressure is good” and therefore small blocks and zero growth are desirable?</em>
> Greg: *fee pressure is an intentional part of the system design and to the best of the current understanding essential for the system’s long term survival. So, uh, yes. It’s good.*

**2016–01–17**

Paul Vigna in *The Wall Street Journal* discussed the demise of XT and rise of Bitcoin Classic:

“[ *Is Bitcoin Breaking Up* ](http://archive.is/lK24o)?”

> *The fight between backers of XT and the original version, now called Core, has been ugly. It has raged on Reddit and social media, users have been tossed off message boards, and there have been anonymous cyberattacks on users and companies. XT started off strongly, but hasn’t gotten near gaining a consensus for change.*

*…*

> *Yet another proposal, this one called* ***Bitcoin Classic, has emerged from the ashes of the XT/Core debate. It is a version of bitcoin that would allow for a two-megabyte limit, with rules put in place to raise it over time. It appears to be quickly winning support.***

> *“Sometimes it takes a crisis to get everyone in a room,” said* [ *Fred Wilson* ](https://archive.is/o/lK24o/topics.wsj.com/person/W/Fred-Wilson/7065) *of Union Square Ventures, a venture-capital firm with bitcoin investments, in a philosophical blog post. “That may be how the block-size debate gets settled.”*

**2016, February**

Cornell’s IC3 group, the Initiative for CryptoCurrencies & Contracts, published “On Scaling Decentralized Blockchains” [[pdf](http://www.initc3.org/files/Scaling2016.pdf)], a position paper which recommends a block size limit of 4MB based on propagation times and bandwidth speeds:

[![](https://cdn-images-1.medium.com/max/1600/0*PrB9c2lCouIbXMhX.)](http://www.initc3.org/files/Scaling2016.pdf)

Paper by Kyle Croman, Christian Decker, Ittay Eyal, Adem Efe Gencer, Ari Juels, Ahmed Kosba, Andrew, Prateek Saxena, Elaine Shi, Emin Gün Sirer, Dawn, and Roger Wattenhofer Published in **Financial Cryptography and Data Security**

That 4MB limit might sound familiar. It’s also the block weight limit for Bitcoin today (as of November 2017) with Segwit activated. In terms of the actual available data in Bitcoin Block today, excluding the coinbase transaction, the number is 3,999,280 bytes [[ref](https://bitcoin.stackexchange.com/questions/54948/after-segwit-activation-what-is-the-largest-block-size-possible/54949#54949)].

**Nov 16th, 2017:** The chart below violates the timeline, but it is important for context. The actual average block size with about 10% Segwit transactions is not much beyond 1.1MB. Proponents of Segwit as a scaling solution claim that with high adoption, average block sizes would be closer to 2MB.

![](https://cdn-images-1.medium.com/max/1600/0*QiGQyWL9UYC1TjDo.)

via Segwit.party

**2016–02–10**

Bitcoin Classic was released, which, with 75% miner support, would raise the limit from 1MB to 2MB.

Vigna wrote again about Classic / XT for the *Wall Street Journal* :

> *Bitcoin Classic has emerged from the ashes of the* [ *XT* ](https://en.wikipedia.org/wiki/Bitcoin_XT) *versus Core debate. It is a version of Bitcoin that would allow for a two-megabyte limit. It appears to be quickly winning support.*

*Around this time,* I ran Bitcoin Classic, and it felt like a fresh start. It was sad to see this temporary bright light at the end of a long tunnel.

**2016–02–11**

Bitcoin Roundtable posted a pr-block size increase article titled “[A Call for Consensus](https://medium.com/@bitcoinroundtable/a-call-for-consensus-d96d5560d8d6)”.

[ *Over the past few months there has been significant attention within the bitcoin ecosystem and beyond on what is…* medium.com](https://medium.com/@bitcoinroundtable/a-call-for-consensus-d96d5560d8d6)

Bitcoin Roundtable represents a massive collection of Bitcoin businesses, exchanges, wallets, miners and mining pools. They specifically mention five positions. Position three requests that Core developers create a roadmap for block size increase:

*3. In the next 3 weeks, we need the Bitcoin Core developers to work with us and clarify the roadmap with respect to a future hard-fork which includes an increase of the block size. Currently we are in discussions to determine the next best steps. We are as a matter of principle against unduly rushed or controversial hard-forks irrespective of the team proposing and we will not run such code on production systems nor mine any block from that hard-fork. We urge everyone to act rationally and hold off on making any decision to run a contentious hard-fork (Classic/XT or any other).*

On this date, Bitcoin Classic’s support from miners had reached 75 percent. The undersigned of the above letter represent 90% of Bitcoin’s hash power, which basically means that they were ready to drop Bitcoin Classic if Core was able to propose a less contentious hard fork option.

[The comments on that post](https://medium.com/@flix1/so-90-of-hashpower-has-signed-this-and-bitcoinclassic-com-2ebc1545e2e5) are worth reading to get a feel for the moment.

In retrospect, this was a moment of setback in the debate: Bitcoin Core developers saw an opportunity to maintain their control over the reference client by promising a block size increase to the Chinese miners. In the interests of not upsetting Bitcoin Core and risking a hard fork, the miners capitulated and stuck with Core, even though Classic was winning more support every day and the miners favored it.

**2016–02–20**

‘Bitcoin Roundtable’ released plan for the introduction of Segwit and a 2MB hard fork, agreed upon at a meeting in Hong Kong:

[ *On February 21st, 2016, in Hong Kong’s Cyberport, representatives from the bitcoin industry and members of the…* medium.com](https://medium.com/@bitcoinroundtable/bitcoin-roundtable-consensus-266d475a61ff)

This plan even included a timeline:

*SegWit is expected to be released in April 2016.*

*The code for the hard-fork will therefore be available by July 2016.*

*If there is strong community support, the hard-fork activation will likely happen around July 2017.*

One of the signatories was:

> *Adam Back*

> *President*

> ***Blockstream***

The hard fork did not happen in July of 2016. Back had been one of the most vocal opponents of the Segwit2x hard fork, yet the document above is essentially the exact same hard fork proposal. It only became clear a day after Bitcoin Cash’s release on Aug. 2, 2017 that Back thinks ‘the market’ agrees a 2MB hard fork is not worth doing, as a block size increase ‘forked’ off already:

[![](https://cdn-images-1.medium.com/max/1600/1*rKmllPuayR2nMINYstDFmw.png)](https://twitter.com/adam3us/status/892717561275666434)

via:[ https://twitter.com/adam3us/status/892717561275666434](https://twitter.com/adam3us/status/892717561275666434)

For more information about Back’s switch against the agreement he signed, see the following article: [ **Adam Back Strongly Advocates Against Agreement He Himself Signed** ](http://www.trustnodes.com/2017/09/28/adam-back-strongly-advocates-agreement-signed)

It included this leaked image:

![](https://cdn-images-1.medium.com/max/1600/0*6vmglUdb7PX_glRG.)

The image shows that one key point of the argument against hard forks for Back’s audience was: “A democracy is two wolves and a lamb voting on what to have for lunch.”

FYI, you’re halfway through this timeline. Thanks for sticking with it. Take a break if you need it.

**2016–2–23**

Slush Pool (which made up for 5 percent of Bitcoin’s hash power at the time) signaled support for Bitcoin Classic. The actual activation threshold was 750 of the last 1000 blocks, and would be cancelled if the number is not hit by 1/1/2018.

[ **Slush Pool Confirms Support For Bitcoin Classic** ](https://themerkle.com/slush-pool-confirms-support-for-bitcoin-classic/)

[ *More and more mining pools are starting to back the Bitcoin Classic solution, as everyone wants to come to a solution…* themerkle.com](https://themerkle.com/slush-pool-confirms-support-for-bitcoin-classic/)

**2016–03–04**

In an example of “coverage” of Bitcoin Classic, Bitcoin Core contributor Peter Todd was asked about Bitcoin Classic, but the creator of Bitcoin Classic was not heard from:

[ **Four Key Disagreements Between Bitcoin Classic and Bitcoin Core — Bitcoin Magazine** ](https://bitcoinmagazine.com/articles/four-key-disagreements-between-bitcoin-classic-and-bitcoin-core-four-key-disagreements-between-bitcoin-classic-and-bitcoin-core-four-key-disagreements-between-bitcoin-classic-and-bitcoin-core-1457106744/)

[ *Bitcoin Core contributor Peter Todd was recently interviewed on episode 34 ofThe Bitcoin Game , and the longtime…* bitcoinmagazine.com](https://bitcoinmagazine.com/articles/four-key-disagreements-between-bitcoin-classic-and-bitcoin-core-four-key-disagreements-between-bitcoin-classic-and-bitcoin-core-four-key-disagreements-between-bitcoin-classic-and-bitcoin-core-1457106744/)

Todd said:

*I think the real difference is that the Bitcoin Core developers — they understand that these tradeoffs are going to happen, at least with current technology — are willing to put the tradeoffs in different places. I would much rather have the tradeoff be that the Bitcoin blockchain layer — the very lowest level — stays highly decentralized. It may get more expensive to use directly, but you counterbalance that by putting the inevitable centralization at a higher level.*

**2016–03–05**

Brian Armstrong, CEO of Coinbase, published the blog post “[ **What Happened At The Satoshi Roundtable”.** ](https://blog.coinbase.com/what-happened-at-the-satoshi-roundtable-6c11a10d8cdf)

[ *Last weekend I attended the Satoshi Roundtable conference along with Charlie Lee and about 70 other members of the…* blog.coinbase.com](https://blog.coinbase.com/what-happened-at-the-satoshi-roundtable-6c11a10d8cdf)

Armstrong was disheartened by the lack of commitment to on-chain scaling at the Satoshi Roundtable meeting in Hong Kong, and his number one recommendation for the community was to hard fork to 2MB under Bitcoin Classic. He had a sad but apt understanding of Bitcoin Core developers:

*Even though core says they are ok with a hard fork to 2MB (they have it on their own roadmap, just very far in the future), they refuse to prioritize it. They prefer to withhold something that could help the network now, because they don’t trust the community to make educated decisions in the future. They view themselves as the central planners of the network, and protectors of the people. They seem ok with watching bitcoin fail, as long as they don’t compromise on their principles.*

His recommendation was:

*The first step is that we need to do an immediate upgrade to 2MB blocks. This is the most realistic short term scaling solution that will buy us time. My belief is that we will either be doing this upgrade now (when there is sufficient lead time for everyone to prepare), or we will be doing it in the midst of an emergency down the road. It is not a matter of if, but when. There is code already available to* [ *accomplish this today* ](https://github.com/bitcoinclassic/bitcoinclassic/releases/tag/v0.11.2.cl1) *. The code is high quality, is written by former core developers, and is already being run in production by a number of bitcoin companies (including Coinbase). By upgrading to Bitcoin Classic it does not mean we need to stay with the Classic team forever, it simply is the best option to mitigate risk right now. We can use code from any team in the future.*

He also explained how he sees Chinese miners being manipulated:

*We need to communicate with the Chinese miners about this upgrade path. They have been misled to believe that only 4–5 people in the world can safely work on the bitcoin protocol, when in fact it is this group that poses the greatest risk for their businesses.*

**2016–3–19**

Bitcoin Classic nodes peaked at 2.3K and had a final hoorah around May 26, 2016.

![](https://cdn-images-1.medium.com/max/1600/0*DAnG3M7FU08JDCGZ.)

**2016–6–8**

[Falcon Network](http://www.falcon-net.org) soft-launched in private beta to relay blocks faster. Miners connect directly to the network to receive blocks quicker:

> Falcon is a novel, fast relay network for disseminating Bitcoin blocks. It connects miners and full nodes and ferries blocks using a novel technique to reduce orphans, which in turn helps miners get the most for their effort, and helps the network efficiently convert the spent energy into security. And ultimately, Falcon helps Bitcoin scale.

![](https://cdn-images-1.medium.com/max/1600/1*w2EbNz_1Q4sN1IdVyQ1WDg.png)

**2016–06–15**

Erik Voorhees, founder of Coinapult, tweeted about block size and average transaction fee:

**2016–7–7**

Matt Corallo releases the FIBRE network, a method to more quickly receive blocks as they are solved:

**2016–07–28**

User GhostOfPermabullPast posted on r/btc about the “Blockstream conspiracy”, asking for proof behind it: [Is there a source that exolains (sic) the whole Blockstream conspiracy hypothesis in detail?](https://www.reddit.com/r/btc/comments/4v26v9/is_there_a_source_that_explains_the_whole/d5uxi5r/)

Now I don’t want to dwell too much on the ‘conspiracy’ posts going around regarding Blockstream. There are hundreds of them. I don’t particularly have an opinion about whether or not Blockstream is an evil megacorp — I actually find the obsession over Blockstream and their employees quite interesting. A community without a central core looks at any centralized group, company, or closed community with suspicion.

User higgletypiggletypop (yes I know these usernames are great) delivered the following:

> I’m not sure it’s really a “conspiracy hypothesis” so much as applied common sense, but the reasoning goes something like this:

> Blockstream is a for-profit corporation. (fact)

> A primary goal of Blockstream Blockstream’s goal, like all for-profit corporations, is to make money. (almost certainly a fact)

> Blockstream employs many core devs. (fact)

> Blockstream’s is all about sidechains (source: https://blockstream.com/fact-sheet/) and hence Blockstream’s plans for making money likely revolve around sidechains.

> Sidechains are needed when the main chain can’t accommodate demand for transactions.

> Blockstream’s interests thus lie in getting to a world where sidechains are needed.

> Blockstream, employing many core devs, guides bitcoin development according to its interests — which are keeping block sizes low so that many transactions are pushed onto sidechains.

> Blockstream’s small-block interests may not coincide with many members of the bitcoin ecosystem who wish, most of all, to see bitcoin grow healthily.

> Now, do I think that the members of Blockstream say to themselves “we must stick with small blocks, bitcoin’s future be damned, because otherwise we’ll never make money?” I don’t, but I do think they’ve thoroughly convinced themselves that small blocks are the only path of the righteous, and this just so happens to line up with their corporate interests. In other words, when asking why members of Blockstream/core don’t seem to be able to honestly engage with arguments for increasing the block size, this quote applies: “”It is difficult to get a man to understand something, when his salary depends upon his not understanding it!” (Upton Sinclair).

> None of this is crazy conspiracy talk. The real conspiracy-theory stuff is that Blockstream is actively trying to kill bitcoin. That I do not believe.

2016–10–31

John Blocke published the article “[ **There Will Be No Bitcoin Split”** ](https://medium.com/@johnblocke/there-will-be-no-bitcoin-split-564f1d60a657) in which they discuss the effects of a hard fork.

[ *Part one of a two part article. The second part can be found here.* medium.com](https://medium.com/@johnblocke/there-will-be-no-bitcoin-split-564f1d60a657)

2016–11–13

John Blocke published “[ **A (brief and incomplete) history of censorship in /r/Bitcoin** ](https://medium.com/@johnblocke/a-brief-and-incomplete-history-of-censorship-in-r-bitcoin-c85a290fe43)” to explain how censorship on the /r/bitcoin subreddit actually happens. The post is actually a great introduction to the relationship between censorship and the block size debate, and how hard forks are disallowed from discussion based on suspicious rules.

2016–11–23

Chinese miner Jiang Zhuo’er published the article “[ **Why We Must Oppose Core’s Segwit Soft Fork, Bitcoin Miner Jiang Zhuo’er Tells You Why!”** ](https://medium.com/@zhangsanbtc/why-we-must-oppose-cores-segwit-soft-fork-bitcoin-miner-jiang-zhuo-er-tells-you-why-28f820d51f98) arguing against Bitcoin Core’s implementation of Segwit.

[ *Translated from the original by Jiang Zhuo’er.* medium.com](https://medium.com/@zhangsanbtc/why-we-must-oppose-cores-segwit-soft-fork-bitcoin-miner-jiang-zhuo-er-tells-you-why-28f820d51f98)

2016–11-from

“I’m not pro classic, and I’m not pro core. Within the next year and a half, we’re going to do Segregated Witness

2016–12–03

Tobes published the article “[ **The Motivation of Core/Blockstream”** ](https://medium.com/@tobesdoe/the-motivation-of-core-blockstream-8ddc44bf8ca3) discussing, you guessed it, the possible motivations of Bitcoin Core and Blockstream and where they intersect.

[ *I’m following the blocksize debate for a very long time now. Like many others I feel that it has been debated for too…* medium.com](https://medium.com/@tobesdoe/the-motivation-of-core-blockstream-8ddc44bf8ca3)

2016–12–21

Jaqen Hash’ghar published the article “[ **Segregated Witness: A Fork Too Far** ](https://medium.com/the-publius-letters/segregated-witness-a-fork-too-far-87d6e57a4179)” analyzing the potential effects of Segregated Witness as a soft fork.

[https://medium.com/the-publius-letters/segregated-witness-a-fork-too-far-87d6e57a4179](https://medium.com/the-publius-letters/gregated-w,tness-a-fork-too-far-87d6e57a4179)

2017–01–28

Luke Dashjr (Core Developer) published a[ Bitcoin Improvement Proposal](https://github.com/luke-jr/bips/blob/bip-blksize/bip-blksize.mediawiki#Rationale) to decrease the block size to 300KB and slowly raise it, hitting the current 1MB size in 2024. He was tasked with implementing hard fork code to raise the limit to 2MB after the Hong Kong agreement but instead took several steps backwards, with a proposal that starts low, and gets to the 1MB limit in 2024. He[ posted this notice](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-January/013496.html) on the developer mailing list.

His notice suggested implementing a series of block size steps, one about every 97 days, and ending at just under 31MB in April 2045. Each step would increase the maximum block size by 4.4%, allowing an overall growth of 17.7% per year. The initial size limit upon activation would depend on when it is activated: for example, if in January 2018, it would begin at about 356K; if in June 2024, it would begin at just over 1MB.

This confused a lot of people on the mailing list, and his proposal didn’t receive much interest or discussion. Was this the only scaling proposal that would emerge from the Hong Kong meeting? It was clear that Bitcoin Core wanted Segwit, and they could only get it with support from miners.

After Back, Blockstream’s CEO, went to China to have a meeting with miners, he told them that he represented Bitcoin Core. They agreed to implement a 2MB hard fork alongside Segwit. The person he (or someone) decided would handle it was LukeJR. Two people wouldn’t work on the same thing at the same time. It was well known that he was “in charge” of writing the code for it. It’s not a false statement at all, it’s a factual objective observation of what has taken place.

The following Reddit thread [has details](https://np.reddit.com/r/Bitcoin/comments/5qo9ie/miners_please_state_your_positions_regarding/) on this event. One excerpt below:

[![](https://cdn-images-1.medium.com/max/1600/1*A78RAvAWuE94yTpREIn4FQ.png)](https://np.reddit.com/r/Bitcoin/comments/5qo9ie/miners_please_state_your_positions_regarding/dd0w2cq/)

https://np.reddit.com/r/Bitcoin/comments/5qo9ie/miners_please_state_your_positions_regarding/dd0w2cq/

A Q&A with Back on 8btc had some[ interesting](http://8btc.com/forum.php?mod=redirect&goto=findpost&ptid=29594&pid=377391) (translated) questions:

![](https://cdn-images-1.medium.com/max/1600/0*dfKPDF0Rv6E4Mp9b.)

“Blockstream bought” indeed. In the vote above, you can see that the ‘Classic’ version has received 42 votes, while ‘Core’ has received 5.

**2017–02–10**

The #dragonsden, which became public during a presentation by Bram Cohen (at [14m:26s](https://youtu.be/aYG0NxoG7yw?t=14m25s) ) is more fuel for the conspiratorial fire:

A post titled “[Inside the Dragon’s Den: Bitcoin Core’s Troll Army](http://telegra.ph/Inside-the-Dragons-Den-Bitcoin-Cores-Troll-Army-04-07)” tries to explain. One key part is the members of the channel:

> …based on the information in the above glimpse of the channel are: BashCo (/r/bitcoin moderator), mrhodl (twitter troll), alp (twitter troll), moli (unknown), belcher (JoinMarket developer), BtcDrak (Bitcoin Core developer/activist) and Bram Cohen. These seven members represent 1/3rd of the total members in the channel.

![](https://cdn-images-1.medium.com/max/1600/1*hFITCaSGIXpmFn8GEMRfvA.png)

**2017–02–12**

User “adambalm” on steemit.com posted about some of the financial connections between Blockstream and their investors’ goals for Bitcoin:

[ **The truth about who is behind Blockstream and Segwit. As the saying goes follow the money. …**
*The too-big-to-fail insurance giant AXA is one of the main owners of Blockstream - and they're throwing around... by…* steemit.com](https://steemit.com/bitcoin/@adambalm/the-truth-about-who-is-behind-blockstream-and-segwit-as-the-saying-goes-follow-the-money)

This notion that developers [shift away from blocksize scaling support](https://np.reddit.com/r/btc/comments/4mlo0z/greg_maxwell_used_to_have_intelligent_nuanced/d3whpu9/) after becoming employed at Blockstream has been repeated for years.

**2017–2–15**

Adem Efe Gencer and Emin Gün Sirer studied the bandwidth, latency, and staleness of Bitcoin nodes through a Cornell study they architected. The team found a bandwidth increase of 1.7x over a single year by measuring nodes:

> The provisioned bandwidth of a node plays a critical role in determining system parameters, such as the maximum block size. The increase in provisioned bandwidth suggests that, for people who were happy with the level of decentralization that Bitcoin exhibited last year, blocks can now be made 1.7X larger without impacting their centralization concerns, assuming that these measurements capture the state of the network.

A common argument against larger block sizes is the idea that large blocks reduce nodes in the network due to bandwidth constraints.

![](https://cdn-images-1.medium.com/max/1600/1*hBMx7mPag5t56-3wybL24Q.png)

via https://cyber.stanford.edu/sites/default/files/efegencer.pdf

**2017–02–26**

In a “wall of text” reply to a newbie asking a question, a most epic explainer of where Bitcoin is socially, politically, economically and in terms of information flow emerged [in the form of a reddit comment](https://www.reddit.com/r/btc/comments/5w8e0i/iamaconfusednoobwithquestions/de8dnx9/). It’s a must-read for understanding this debate. Here’s a snippet:

*Blockstream and it’s employees started lobbying the community by paying for conferences about scaling bitcoin, but with the very very strange rule that no decisions could be made and nothing complete solutions could be proposed. These conferences were likely strategically (and successfully) created to stunt support for the scaling software Gavin and Mike had released by forcing the community to take a “lets wait and see what comes from the conferences” kind of approach. Since no final solutions were allowed at these conferences, they only served to hinder and splinter the communities efforts to find a solution. As the software Gavin and Mike released called BitcoinXT gained support it started to be attacked. Users of the software were attack by DDOS. Employees of Blockstream were recommending attacks against the software, such as faking support for it, to only then drop support at the last moment to put the network in disarray. Blockstream employees were also publicly talking about suing Gavin and Mike from various different angles simply for releasing this open source software that no one was forced to run. In the end Mike Hearn decided to leave due to the way many members of the bitcoin community had treated him.*

**2017–02–27**

John Blocke published the article **“** [ **/r/Bitcoin Censorship, Revisited”** ](https://medium.com/@johnblocke/r-bitcoin-censorship-revisited-58d5b1bdcd64) again highlighting censorship within the r/Bitcoin subreddit.

[ *Note: This post is meant as a follow-up to my original article, A (brief and incomplete) history of censorship on /r…* medium.com](https://medium.com/@johnblocke/r-bitcoin-censorship-revisited-58d5b1bdcd64)

**2017–03–28**

When asked about his proposal for 2MB plus Segwit,[ Luke DashJR replied](https://archive.is/2voL3) that it was rejected after discussion with “the community.”

![](https://cdn-images-1.medium.com/max/1600/0*ADtlwi02BF2CgQUG.)

Was this pull request setup to fail? Or is consensus-building not really Core’s forte? Read comments on this pull request below:

[[bitcoin-dev] Three hardfork-related BIPs](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-January/013496.html) by *Luke Dashjr*

Note that this is the only hard fork proposal which involved a block size increase listed in this ‘Hard Fork Research’ page:[ https://bitcoinhardforkresearch.github.io](https://bitcoinhardforkresearch.github.io)

**2017–3–31**

The Segwit 2MB proposal was born out of the ashes of the Hong Kong agreement (in February 2017), and this proposal included both a Segwit soft fork, and the promise of a 2MB increase via hard fork:

[ **[bitcoin-dev] Segwit2Mb — combined soft/hard fork — Request For Comments** ](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-March/013921.html)

[ *Hi everyone, Segwit2Mb is the project to merge into Bitcoin a minimal patch that aims to untangle the current conflict…* lists.linuxfoundation.org](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-March/013921.html)

**2017–04–06**

The ASICBoost controversy was born. A potential exploit of the proof of work algorithm in Bitcoin (which is impossible with Segwit), enabled by means of a soft fork:

[ **ASICBoost, the reason why Bitmain blocked Segwit.** ](https://medium.com/@WhalePanda/asicboost-the-reason-why-bitmain-blocked-segwit-901fd346ee9f)

2017–04–08

Nick Szabo tweeted about the politics behind the debate:

![](https://cdn-images-1.medium.com/max/1600/1*kfcRvtkvbtKntmDaUQkWLw.png)

**2017–04–18**

ViaBTC (Bitcoin miner) published the article “[ **Why we don’t support SegWit** ](https://medium.com/@ViaBTC/why-we-dont-support-segwit-91d44475cc18)” and also goes into detail about Segwit’s technical debt, and the need for diversity of development teams:

[ *SegWit doesn’t solve the most urgent capacity issue* medium.com](https://medium.com/@ViaBTC/why-we-dont-support-segwit-91d44475cc18)

> As an implementation reference for Bitcoin, Bitcoin Core was of significant influence in the community. However, their influence has long been overrated by their actions. By abusing their previous influence, they’ve obstructed Bitcoin block size increase from happening, against the will of the community. Core team has in some cases explicitly, supported censorship of Bitcoin’s mainstream forums, along with banning of many prominent developers, businesses, and community members who have different opinions with Core’s current roadmap. Today, Bitcoin is in urgent need of diversified dev teams and implementations to achieve decentralization in Bitcoin development.

2017–4–23/25

Digital Currency Group published the article “[ **Bitcoin Scaling Agreement at Consensus 2017** ](https://medium.com/@DCGco/bitcoin-scaling-agreement-at-consensus-2017-133521fe9a77)”.

This is referred to as ‘The New York Agreement’ and spawned the Segwit2x implementation by the plan to follow through with these upgrades to the Bitcoin Network:

> Activate Segregated Witness at an 80% threshold, signaling at bit 4

> Activate a 2 MB hard fork within six months

Signatories to this proposal included:

> The group of signed companies represents a critical mass of the bitcoin ecosystem. As of May 25, this group represents:

> 58 companies located in 22 countries

> 83.28% of hashing power

> 5.1 billion USD monthly on chain transaction volume

> 20.5 million bitcoin wallets

Opponents of this proposal called it a ‘Corporate takeover’ of Bitcoin decided by a few individuals.

**2017–05–01**

Rick Falkvinge, founder of the Swedish Pirate Party, published the blog post “[ **Blockstream having patents in Segwit makes all the weird pieces of the last three years fall perfectly into place** ](https://falkvinge.net/2017/05/01/blockstream-patents-segwit-makes-pieces-fall-place/)”.

**2017–05–14**

Jonald Fyookball published the article “[ **An Open Letter to Bitcoin Miners** ](https://keepingstock.net/an-open-letter-to-bitcoin-miners-c260467e1f0)”.

**2017–5–2**

Back, the CEO of Blockstream [suggested](https://twitter.com/Satoshi_N_/status/859406615912615937?ref_src=twsrc%5Etfw&ref_url=https%3A%2F%2Fmedium.com%2Fmedia%2Ff18fc4a12313d52de98747e8c6b401c5%3FpostId%3D8874363de28d) freezing the ‘base layer’ of Bitcoin in a Twitter DM:

![](https://cdn-images-1.medium.com/max/800/1*eXpmZj9nJJQIxAAh-RFTvg.png)

![](https://cdn-images-1.medium.com/max/800/1*XF1BuIhVl0Mf68P_VARS2w.png)

![](https://cdn-images-1.medium.com/max/800/1*MYfc_P5lQessZ8O52oMaHg.png)

**2017–05–09**

Woobull.com [published](http://woobull.com/bitcoins-scaling-debate-deadlock-fueling-an-alt-coin-bubble-infographic/) an infographic on transaction capacity, block size and the fall of Bitcoin’s market cap dominance in a crowded altcoin market:

![](https://cdn-images-1.medium.com/max/1600/0*1EYMMS99PKlMioGl.)

[ **Bitcoin’s scaling debate deadlock fueling an altcoin bubble [infographic]** ](http://woobull.com/bitcoins-scaling-debate-deadlock-fueling-an-alt-coin-bubble-infographic/)

[ *I’ve put together this infographic to help explain the 8x bubble that altcoins has seen in the last two months. Two…* woobull.com](http://woobull.com/bitcoins-scaling-debate-deadlock-fueling-an-alt-coin-bubble-infographic/)

2017–5–10

Jameson Lopp goes deep into the difficulty of estimating fees:

[ **The Challenges of Bitcoin Transaction Fee Estimation**
*The History of Bitcoin Transaction Fees* blog.bitgo.com](https://blog.bitgo.com/the-challenges-of-bitcoin-transaction-fee-estimation-e47a64a61c72)

You can view the average fees paid [in a chart here](https://p2sh.info/dashboard/db/fee-estimation?panelId=1&fullscreen&orgId=1).

**2017–06–04**

Reddit user BitAlien posted to r/btc about Blockstream’s influence over Bitcoin and its connection to legacy banks:

**2017–06–05**

Reddit user zsaleeba posted to r/btc about the notion that Blockstream might be using Segwit to take over Bitcoin:

**2017–06–10**

Reddit user BeijingBitcoins posted to r/btc about Bitcoin’s high transaction fees:

[Average Bitcoin Transaction fee: $5](https://www.reddit.com/r/btc/comments/6gek0z/averagebitcointransactionfeeisnowabove_five/).

**2017–06–26**

Jimmy Song published the article: “[ **Segwit2x: What you need to know about the 2x Hard Fork (aka 2MB non-Segwit Transaction Capacity per…** ](https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce)”.

[ *When I wrote my last article on Segwit2x, I concluded with questions about the lack of clarity around the 2x part of…* medium.com](https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce)

**2017–06–26**

**Matthew Haywood published the article “** [ **The Road to Segwit Activation — UASF, Segwit2x and Segwit Signalling Explained** ](https://medium.com/@wintercooled/the-road-to-segwit-activation-uasf-segwit2x-and-segwit-signalling-explained-2ff00488b7cb) **”.**

**2017–07–02**

User lexiconical published the article “[ **Seg-Wit Is A Trojan Horse — Bitcoin Scaling Debate Explained** ](https://steemit.com/bitcoin/@lexiconical/seg-wit-is-a-trojan-horse-bitcoin-scaling-debate-explained)” to steemit.com.

[https://steemit.com/bitcoin/@lexiconical/seg-wit-is-a-trojan-horse-bitcoin-scaling-debate-explained](https://steemit.com/bitcoin/@lexiconical/g-wit-is-a,trojan-horse-bitcoin-scaling-debate-explained)

**2017–07–11**

John Stuart Millibit published the article “[ **Cryptocurrency for rent** ](https://medium.com/@john.s.millibit/cryptocurrency-for-rent-ebf8b92ba2ab)”.

[ *Rent-seeking. There is a word you don’t use everyday.* medium.com](https://medium.com/@john.s.millibit/cryptocurrency-for-rent-ebf8b92ba2ab)

The article included this image:

![](https://cdn-images-1.medium.com/max/1600/1*9CXRMKuGgc0yML2nc6985Q.jpeg)

**2017–07–15**

[A great overview](https://np.reddit.com/r/Buttcoin/comments/6ndfut/buttcoinisdecentralizedin5_nodes/dk9c27f/) by [jstolf](https://np.reddit.com/user/jstolfi) regarding what Segwit fixed, why it was deployed as a soft fork, and how transaction malleability needed to be fixed with a soft fork. Also a great discussion of Greg Maxwell’s endeavors at Blockstream which sought to prove the efficiency of the fee market:

> During the backlogs, the fees and delays are completely unpredictable, and a large fraction of the transactions are inevitably delayed by days or weeks. During the intemezzos, there is no “fee market’ because any transaction that pays the minimum fee (a few cents) gets confirmed in the next block.

> That is what Mike predicted, by theory and simulations — and has been going on since Jan/2016, when the incoming non-spam traffic first hit the 1 MB limit. However, Greg stubbornly insists that it is just a temporary situation, and, as soon as good fee estimators are developed and widely used, the “fee market” will stabilize. He simply ignores all arguments of why fee estimation is a provably unsolvable problem and a stable backlog just cannot exist. He desperately needs his stable “fee market” to appear — because, if it doesn’t, then his entire two-layer redesign collapses.

The two-layer redesign Jstolf refers to is the sidechain work Greg Maxwell at Blockstream is developing.

**2017–07–17**

Eric Wall published the article “[ **Bitcoin UASF/Segwit2x/BitcoinABC Flowchart of 201 7 — BIP91 false signaling edition** ](https://medium.com/@ercwl/bitcoin-uasf-segwit2x-bitcoinabc-flowchart-of-2017-aead83d92a49)” and included the chart below.

![](https://cdn-images-1.medium.com/max/1600/0*9vR5WK15b6t-Za2m.)

[See? Bitcoin is easy. Image by Eric Wall](https://image.ibb.co/ndiGVF/Bitcoin_flowchart_2017_revised.png).

**2017–07–20**

Jonald Fyookball published the article “[ **The Upcoming Bitcoin Cash Hard Fort is Great News for Almost Everyone** ](https://medium.com/@jonaldfyookball/the-upcoming-bitcoin-cash-hard-fork-is-great-news-for-almost-everyone-354525ecc539)”.

[ **The Upcoming Bitcoin Cash Hard Fork is Great News for Almost Everyone**
*You may not be aware, but Bitcoin is forking on August 1st with the UAHF “Bitcoin Cash”.* medium.com](https://medium.com/@jonaldfyookball/the-upcoming-bitcoin-cash-hard-fork-is-great-news-for-almost-everyone-354525ecc539)

**2017–07–24**

Jimmy Song writes the [Bitcoin Tech Talk](https://bitcointechtalk.us16.list-manage.com/subscribe?u=055ecd726a069b736a0053297&id=f94fc485ec) newsletter and maintains a technical and unbiased viewpoint on hard forks. While others he joins on the [World Crypto Network](https://www.youtube.com/user/WorldCryptoNetwork) Youtube channel have nothing but distaste for Bitcoin Cash, Song has kept his head above the mudslinging. He published the article “[ **Bitcoin Cash: What You Need to Know** ](https://medium.com/@jimmysong/bitcoin-cash-what-you-need-to-know-c25df28995cf) **.** ”

**2017–07–25**

[ *Based on Blockstream’s behavior in the Bitcoin community, I have become absolutely certain that Segwit contains patents…* falkvinge.net](https://falkvinge.net/2017/05/01/blockstream-patents-segwit-makes-pieces-fall-place/)

**2017–08–1**

[Bitcoin Cash](https://www.bitcoincash.org/) forked away from Bitcoin with 8MB blocks. The hard fork went off without a hitch.

**2017–8–07**

Anticipating the success of the Segwit2X project, TheBlueMatt (Matt Corallo) created a pull request to disconnect from nodes which *in the future* signal that they support Segwit2x. “[ **Disconnect network service bits 6 and 8 until Aug 1, 2018 by TheBlueMatt · Pull Request #10982 …** ](https://github.com/bitcoin/bitcoin/pull/10982)”

![](https://cdn-images-1.medium.com/max/1600/1*WTt60hg03CIfnVcesJqyAg.png)

This was a patch to prematurely segment the network into 1 MB-supporting nodes and 2 MB / Segwit2X-supporting nodes. Bitcoin clients running version 0.15 of Bitcoin Core included this change. This was also discussed in the Segwit2x repository:

[ **New Network Magic · Issue #99 · btc1/bitcoin**
*btc1 really should add some code to more clearly prevent nodes from connecting to other networks, making sure…* github.com](https://github.com/btc1/bitcoin/issues/99#issuecomment-320450248)

**2017–08–08**

Segwit activated via soft fork.

[ **“It’s Official: Segregated Witness Will Activate on Bitcoin — CoinDesk** ](https://www.coindesk.com/its-official-segregated-witness-will-activate-on-bitcoin/) **”**

**2017–08–13**

A quick clip starring Ethereum founder Vitalik Buterin was posted on YouTube regarding /r/Bitcoin censorship:

Transcription:

> I mean I definitely think the censorship on the Bitcoin subreddit is very unfortunate and I do think that it’s like very contrary to the kind of values that we want to have and support in the cryptocurrency and blockchain ecosystem so if for example if you look at the most the most recent Bitcoin cash hard fork, basically all discussion of it was banned and it was put into and one single thread where they called the coin Bcash — right and you know this is a deliberate tactic to try to make it sound like you know this is just an alt coin, and not very connected to Bitcoin. You know you see like a lot of smaller examples of this sort of thing so I mean I do believe that there’s a lot of people in both the Bitcoin ecosystem and many other crypto ecosystems that are probably definitely not happy about this sort of thing.

**2017–08–16**

Pete Rizzo published the article “[ **Block 494,784: Segwit2x Developers Set Date for Bitcoin Hard Fork — CoinDesk** ”.](https://www.coindesk.com/block-494784-segwit2x-developers-set-date-bitcoin-hard-fork/)

[ *The developers behind Segwit2x, a controversial plan to increase the transaction capacity of the bitcoin blockchain…* www.coindesk.com](https://www.coindesk.com/block-494784-segwit2x-developers-set-date-bitcoin-hard-fork/)

**2017–08–19**

Reddit user X-88 posted to r/btc: [“](https://www.reddit.com/r/btc/comments/6uoq7b/ockstreamb,tcoin_core_wants_to_force_everyone/)[Blockstream/Bitcoin Core wants to force everyone to use their patented sidechain](https://www.reddit.com/r/btc/comments/6uoq7b/blockstreambitcoin_core_wants_to_force_everyone/)”.

**2017–08–19**

Roger Ver posted a YouTube video on the Economic Code of Bitcoin and Bitcoin Cash.

**2017–08–20**

Reddit user MobTwo posted to r/btc an open letter to Greg and other Core developers:

[https://www.reddit.com/r/btc/comments/6uxwts/dear *greg* and *other* core_developers/](https://www.reddit.com/r/btc/comments/6uxwts/ar_greg_an,_other_core_developers/)

**2017–08–22**

[Olivier Janssens](https://medium.com/u/fb16a7233e8e) published the article “[ **Why “non-mining full nodes” are a terrible idea** ](https://medium.com/@olivierjanss/why-non-mining-full-nodes-are-a-terrible-idea-ad3c49f7a7b6)” to explain the disadvantages of running full nodes. He went into detail about why people might feel like they are economically participating, or even ‘voting’ when running full nodes, while they’re actually doing neither.

[ *In the early days of Bitcoin, there was no-such thing as a “non-mining full node”. Every miner was a node and every…* medium.com](https://medium.com/@olivierjanss/why-non-mining-full-nodes-are-a-terrible-idea-ad3c49f7a7b6)

Here’s some additional information to provide background to this article. The role of nodes in Bitcoin is very misunderstood. While it may feel empowering to run a full node to verify transactions, verification can also be done by running a light client, or a wallet running Simple Payment Verification mode (SPV). This requires a fraction of the resources to monitor incoming transactions, and offers the same security, since an SPV client is typically connected to a number of servers. [Electrum](https://electrum.org/#home), the most popular SPV client, connects to 10 nodes by default. Since Janssens’s article covers a topic very important to the scaling debate, it’s also worth reading the back-and-forth on finer points where Olivier [addressed some comments](https://medium.com/@olivierjanss/first-of-all-i-want-to-applaud-you-for-writing-a-proper-response-10f5df614e0f).

Also on this date, core developer Eric Lombrozo[ called the hard fork proposal of Segwit2x an **attack** on Bitcoin](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-August/000259.html):

*As long as a lot of people still want the legacy chain, attempts to destroy it will be treated as an attack on the property of all these people. It constitutes a serious cyberattack and decisive action against it, both technical and legal, has been prepared.*

This is where Bitcoin Core developers start enormous hand waving and FUD-production as they come to realize what losing control over the reference client might mean.

[ **[Bitcoin-Segwit2x] Bitcoin Cash’s mandatory replay protection — an example for B2X** ](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-August/000259.html)

[ *To be clear, it isn’t up to any of us. A good portion of the community wants to keep the legacy chain. NYA signers are…* lists.linuxfoundation.org](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-August/000259.html)

**2017–8–24**

Luke Dashjr tweets that Segwit should be avoided for normal transactions, and instead only be used for Lightning:

**2017–8–28**

Reddit user PretenseOfKnowldge posted [“](https://archive.is/6DkOY)[8 times Core told people Segwit is a Blocksize Increase](https://archive.is/9I6PY)”, which is worth sharing as a key reference in this debate (even though many authors of the posts he shared were not ‘core’ developers).

Those claims are listed below:

“SegWit is a block size increase. Prove it isn’t.”

https://twitter.com/excellion/status/847273464461352960

“Segwit is a 2MB block size increase, full stop.”

[https://www.reddit.com/r/btc/comments/6tcrr2/why_transaction_malleability_cant_be_solved/dlju9dx/](https://archive.is/o/6DkOY/https://www.reddit.com/r/btc/comments/6tcrr2/why_transaction_malleability_cant_be_solved/dlju9dx/)

“SegWit is a blocksize increase. Period.”

[https://www.reddit.com/r/Bitcoin/comments/5e0ls7/segwit_vs_block_size_increase_in_a_nutshell/da8sk1p/](https://archive.is/o/6DkOY/https://www.reddit.com/r/Bitcoin/comments/5e0ls7/segwit_vs_block_size_increase_in_a_nutshell/da8sk1p/)

“Really? Still haven’t caught on that segwit is a blocksize increase? Either you are intentionally trying to mislead readers or completely incompetent. Which is it?”

[https://medium.com/@compricadev/really-still-havent-caught-on-that-segwit-is-a-blocksize-increase-ba111c2f2130](https://archive.is/o/6DkOY/https://medium.com/@compricadev/really-still-havent-caught-on-that-segwit-is-a-blocksize-increase-ba111c2f2130)

“segwit is a blocksize increase. Poll should be, after doubling blocksize w/ segwit, do we want to double it again in 90 days?”

https://twitter.com/petertoddbtc/status/887656660801605633

“Is SegWit a block size increase? Yes!”

[https://segwit.org/is-segwit-a-block-size-increase-705df6a8731d](https://archive.is/o/6DkOY/https://segwit.org/is-segwit-a-block-size-increase-705df6a8731d)

“Segwit *is* an actual block size increase”

![](https://cdn-images-1.medium.com/max/1600/1*JO_l7S0MgXgyG0mhgUsB5A.png)

“Segwit is a 2MB block-size increase.”

[https://twitter.com/adam3us/status/848319001491120129](https://archive.is/o/6DkOY/https://twitter.com/adam3us/status/848319001491120129)

“#SegWit is an *actual* block size increase”

[https://twitter.com/eric_lombrozo/status/855156121593495552](https://archive.is/o/6DkOY/https://twitter.com/eric_lombrozo/status/855156121593495552)

“This table by @sysmannet actually shows that #segwit will increase the #bitcoin block size to almost 2 MB.”

**2017–08–30**

Jonald Fyookball published the article “[ **Why does Bitcoin have Ridiculously High Fees and Slow Confirmations?** ](https://medium.com/@jonaldfyookball/why-does-bitcoin-have-ridiculously-high-fees-and-slow-confirmations-e3fd58258a6d)”.

[ **Why does Bitcoin have Ridiculously High Fees and Slow Confirmations?**
*If you’ve tried to use Bitcoin recently, you’ve probably noticed its getting expensive. The average fee spiked as high…* medium.com](https://medium.com/@jonaldfyookball/why-does-bitcoin-have-ridiculously-high-fees-and-slow-confirmations-e3fd58258a6d)

**2017–10–11**

Bitcoin.org issued a warning about services that support Segwit2x:

[ ***Beware of Bitcoin’s possible incompatibility with some major services*** ](https://bitcoin.org/en/alert/2017-10-09-segwit2x-safety)

[Beware of Bitcoin’s possible incompatibility with some major servicesbitcoin.org](https://bitcoin.org/en/alert/2017-10-09-segwit2x-safety)

**2017–10–23**

David Farmer, the Director of Communications at CoinBase, published the article “[ **Timeline and Support — Bitcoin Segwit2x and Bitcoin Gold** ”.](https://blog.coinbase.com/timeline-and-support-bitcoin-segwit2x-and-bitcoin-gold-eda72525efd)

[ *We wanted to give customers another update on two upcoming Bitcoin forks — Bitcoin Segwit2x and Bitcoin Gold. You can…* blog.coinbase.com](https://blog.coinbase.com/timeline-and-support-bitcoin-segwit2x-and-bitcoin-gold-eda72525efd)

**2017–10–24**

Exchanges and wallets put out announcements regarding how they will treat the fork. A common theme is that markets will use the accumulated difficulty:

[Gemini](https://gemini.com/blog/upcoming-bitcoin-hard-fork-modified-exchange-operations/): “The cumulative computational difficulty is an objective and observable metric that is impossible to fake or “game.” It may not be a usable framework in all future chain split situations, but it works for this one.” — Oct 24

[Coinbase / GDAX](https://blog.coinbase.com/clarification-on-the-upcoming-segwit2x-fork-d3c0f545c3e0): “ **We are going to call the chain with the most accumulated difficulty Bitcoin.” — Oct 24**

[In Bitfinex’s announcement](https://www.bitfinex.com/posts/223), they have chosen to ignore hashing power, and will stick with a name: “The incumbent implementation (based on the existing Bitcoin consensus protocol) will continue to trade as BTC even if the B2X chain has more hashing power.”

So what this essentially means is that after a certain period of time, exchanges will need to declare “This chain, with a block height of X, and a mining difficulty of X, is what we are talking about when we use use the name *Bitcoin.* ” Other exchanges might call that same chain *B2X* if Segwit2x becomes the dominant chain in terms of hash power.

[See this post from Coinigy](https://blog.coinigy.com/2017/10/comprehensive-list-of-exchange-segwit2x-stances/) for more stances and positions.

[ **Will This Battle For The Soul Of Bitcoin Destroy It?** ](https://www.forbes.com/sites/laurashin/2017/10/23/will-this-battle-for-the-soul-of-bitcoin-destroy-it/#1ab4ffef3d3c)

[ *As Bitcoin hit a new record high less than two weeks ago, long-time “hodlers” (an inside joke in crypto based on a typo…* www.forbes.com](https://www.forbes.com/sites/laurashin/2017/10/23/will-this-battle-for-the-soul-of-bitcoin-destroy-it/#1ab4ffef3d3c)

**2017–10–25**

Marc Bevand published the blog post “[ **The case for increasing Bitcoin’s block weight limit** ”.](http://blog.zorinaq.com/block-increase-needed/)

[ **The case for increasing Bitcoin's block weight limit**
*March 2017 was a significant moment for Bitcoin: the average block size bumped into the 1MB limit, stunting the growth…* blog.zorinaq.com](http://blog.zorinaq.com/block-increase-needed/)

It includes the following chart:

![](https://cdn-images-1.medium.com/max/1600/1*Qgu5LR_pmzF8TcWv5mIiOA.png)

Also on this date, Slushcz tweeted at Coinbase directly refuting the idea that hash power defines Bitcoin:

2017–10–29

ThePiachu’s Bitcoin Blog published a post laying it all out. Discussing Blockstream, miners, and users, it states:

*Both sides of this debate get their money from the same source — transaction fees. Blockstream wants more transactions to flow through their proprietary service to collect more fees from institutions and individuals. The miners on the other hand benefit from more transactions taking place on the blockchain — they earn transaction fees only for the transactions that are included in the block and get nothing from off-chain transactions until they come back onto the chain. With finite amount of money flowing through the network, this is a classic zero-sum game — the more transactions flow through your preferred channel, the more money you have and the less money your opponent has.*

[ **Blockstream vs miners — looking at the incentives around the Segwit2x fork** ](https://tpbit.blogspot.de/2017/10/blockstream-vs-miners-looking-at.html)

[ *The past few months in the Bitcoin community have been filled with discussion of an upcoming hardfork — Segwit2x. There…* tpbit.blogspot.de](https://tpbit.blogspot.de/2017/10/blockstream-vs-miners-looking-at.html)

2017–11–01

An anonymous poster published “[ **An open letter to Bitcoin miners from another miner** ](https://theflippening.github.io/open-letter-to-bitcoin-miners-from-another-miner/)” asking miners to build up Bitcoin’s difficulty and immediately switch to mining Bitcoin cash in an effort to tank original Bitcoin’s value and freeze its blocks. It encourages a fresh start with a block chain with the enormous capacity of 8MB, the potential for huge blocks down the line, and none of the technical debt of Segregated Witness:

[ *For Bitcoin to succeed and gain total market dominance there should only be one Bitcoin. For merchants it is too…* theflippening.github.io](https://theflippening.github.io/open-letter-to-bitcoin-miners-from-another-miner/)

( *In retrospect, this didn’t happen, and* [ *the hard fork in November 2017* ](https://www.bitcoinabc.org/november) *reduced the chaos caused by constantly-shifting Bitcoin Cash difficulty.)*

**2017–10–31**

This date marked [nine years](https://news.bitcoin.com/satoshi-nakamotos-brilliant-white-paper-turns-9-years-old/) since Satoshi Nakamoto published the Bitcoin whitepaper.

(FYI — If Satoshi has access to all his 1 million Bitcoin and Bitcoin Cash, he’s worth $8.7 billion.)

Assuming: (1,000,000 BTC * $7,500) + (1,000,000 Bitcoin Cash * $1,209)

**2017–11–1**

Brian Hoffman published the article **“** [ **Segwit2x: You’re fucked if you do, you’re fucked if you don’t** ”.](https://techburst.io/segwit2x-youre-fucked-if-you-do-you-re-fucked-if-you-don-t-6655a853d8e7)

[ *Over the last few months there has been no project or company that has suffered more dramatically due to Segwit2x and…* techburst.io](https://techburst.io/segwit2x-youre-fucked-if-you-do-you-re-fucked-if-you-don-t-6655a853d8e7)

**2017–11–3**

Back, the CEO of Blockstream, started [soliciting](https://twitter.com/adam3us/status/924637643035545601?ref_src=twsrc%5Etfw&ref_url=http%3A%2F%2Fwww.livebitcoinnews.com%2Fadam-back-wants-offload-b2x-coins-31-ratio%2F) wagers for what he calls ‘B2X’ coins, both [on Reddit](https://www.reddit.com/r/btc/comments/79jdew/seeking_buyers_of_b2x_coins_price_3_for_1_in/) and Twitter:

![](https://cdn-images-1.medium.com/max/1600/0*zd86tlf0koclDPYJ.)

Back shared this offer to every communication platform he has access to, (except /r/bitcoin, which has censored his post). He also posted his offer [to the developer mailing list](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-October/000616.html).

He was called out on this odd behavior:

**2017–11–8**

After wallets, exchanges, and anyone hoping to interact with the Segwit2x network had upgraded, or was in the process of upgrading their wallets to support two chains (and in[ many cases](https://blog.bitgo.com/bitgos-segwit2x-plan-bb8f17e972d3) handle[ replay protection](https://bitcoin.stackexchange.com/a/61213/35)), Segwit2x was cancelled by six men:

![](https://cdn-images-1.medium.com/max/1600/0*FGyBXjWOttxzE2FZ.)

(This is the original formatting of the email sent by Mike Belshe to the [Bitcoin Segwit2x](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-November/000685.html) mailing list.)

Read it here:[https://lists.linuxfoundation.org/pipermail/bitcoin-Segwit2x/2017-November/000685.html](https://lists.linuxfoundation.org/pipermail/bitcoin-segwit2x/2017-November/000685.html)

(Also take note of replies promising to still follow through with the fork.)

Were the undersigned aware of the bugs in btc1 ([explained by Jimmy Song here](https://bitcointechtalk.com/segwit2x-bugs-explained-8e0c286124bc) 12 days later) which would have cause a total chain failure had Segwit2x proceeded? We don’t yet know.

**2017–11–10**

Jihan Wu, who by some measures controls the majority of hashpower on the Bitcoin Network, tweeted the following:

Luke Dashjr spent the next two days suggesting a change to the Proof of Work algorithm behind Bitcoin, as seen in this tweet:

**2017–11–11**

Andreas Antonopoulos (@aantonop) tweeted about Bitcoin and Bitcoin Cash coexisting and serving different purposes, while Andresen tweeted about what Bitcoin Cash means to him:

![](https://cdn-images-1.medium.com/max/1600/0*FEMvrFOV-2X5MYwZ.)

**2017–11–12**

The Hashrate of Bitcoin had fallen precipitously, the mempool had 167K pending transactions, and miners had apparently switched over to focusing on Bitcoin Cash. The below chart is from [fork.lol](https://fork.lol/pow/hashrate):

![](https://cdn-images-1.medium.com/max/1600/0*52tmwC9d0kBd8qEp.)

[More info about this phenomenon here](https://jaredschlar.blogspot.com/2017/11/todays-bitcoin-highlights.html).

**2017–11–12**

We find ourselves in a situation where a philosophical and economic wedge has been driven between those who feel protected by the constricted control of the block size, and those who feel free with Bitcoin Cash to do as they please. Falkvinge posted a statement on the *un* governance in Bitcoin Cash as a direct response to the failed governance model of the Bitcoin Core community:

Read the PDF of the statement here:[ https://www.bitcoincash.org/letter-from-the-ceo.pdf](https://www.bitcoincash.org/letter-from-the-ceo.pdf)

Falkvinge calls out Replace by Fee, the segregation of witness data (Bitcoin Cash does not have Segwit), and more. It’s worth a read in understanding this debate.

**2017–11–14**

All of a sudden, Back stated that he supports the idea of a Block size increase:

![](https://cdn-images-1.medium.com/max/1600/0*vRfd6yXZkEuIzgRD.)

https://twitter.com/adam3us/status/930102757540765697

**2017–11–20**

The limit continues to be a point of discussion during conversations about the block size:

**2017–11–30**

A great read by Rusty Russell delineating the different phases in Bitcoin, with a specific focus on the rise of the fee market and decline of low-value transactions. The eras:

#### First Era: Satoshi’s Free Offer (2009–2014)

> In the early years of bitcoin, it was obscure and unvaluable. Demand was so tiny you could send any amount for free.

#### Second Era: Satoshi’s Subsidy (We Are Here)

> The bursty statistical nature of block production, combined with the volatile market of bitcoin, began to produce intermittent capacity issues. These had been previously dealt with by code optimizations and tweaking settings by miners; now they became more regular and significant, causing rising awareness that the First Era was at risk.

#### Third Era: Self Sufficiency (2028? onwards)

> User-facing businesses established in the First Era who flourished into the Second Era will find the Third Era extremely difficult.

[ **The Three Economic Eras of Bitcoin**
*The way the bitcoin ecosystem will play out is written in the mathematics of its consensus rules; we should all know…* medium.com](https://medium.com/@rusty_lightning/the-three-economic-eras-of-bitcoin-d43bf0cf058a)

**2017–12–2**

[In a Q&A session](https://www.youtube.com/watch?v=DHc81OL_hk4&feature=youtu.be&t=21136), Adam Back is asked about what restaurants can do to work around high fees. He responds by first suggesting being an early adopter of the lightning network (which has no wallets or channels at the time) and then suggests that people keep a ‘tab’ of what is spent and folks could settle that tab as needed:

> “So I mean for today, You could have, some bitcoin business have a tab, so you pay them and you work your tab there and presumably you can cash your tab out if you don’t use it. If you have repeat custom… or maybe the shops in the local area could make a shared tab or something in anticipation of… you know somebody in the local area … technology expert could make a local bitcoin tab that’s interoperable between the shops and some sort of app to do it.”

**2017–12–22**

![](https://cdn-images-1.medium.com/max/1600/1*_uW9mMsLDNw3SitnM3F4LQ.png)

As average fees on Bitcoin approach 55$ per transaction, Melvin Carvalho [writes](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2017-December/015455.html) on the Bitcoin dev mailing list that Bitcoin had reached a problematic point where the cumulative fees per block have almost cross the block reward. At this time, fees make up about 50% of the reward. Just a couple weeks prior, that portion was merely 10%. Carvalho writes:

> *While this bodes well for the long term security of the coin, I think there is some legitimate concern that the fee per tx is prohibitive for some use cases, at this point in the adoption curve.*

In response, Greg Maxwell writes:

> Personally, I’m pulling out the champaign that market behaviour is indeed producing activity levels that can pay for security without inflation, and also producing fee paying backlogs needed to stabilize consensus progress as the subsidy declines.

It really is a special kind if logical gymnastics, best summed up here:

**2018–12–26**

In [a comment](https://medium.com/@VitalikButerin/he-imagines-a-world-in-which-crypto-political-and-legal-processes-are-necessarily-going-to-go-fb073b80dd7e) on [a post](https://medium.com/cryptolawreview/against-szabos-law-for-a-new-crypto-legal-system-d00d0f3d3827) by Vlad Zamfir, Vitalik Buterin reiterates his belief that failure to raise the block size caused huge damages to Bitcoin:

> Now I personally can see that it’s not axiomatically true that doing nothing is safest, especially in the context of a changing environment (for example I continue to believe that Bitcoin’s *failure* to raise its blocksize by a significant amount in 2016–17 was a travesty and a great violation of many people’s expectations of the protocol, and one that led to more [total losses due to excess txfees](https://www.blockchain.com/charts/transaction-fees-usd?timespan=2years) than the amount lost in the MtGox hack), but this is the argument that you need to be arguing against.

2020–1–4

[ **[Cryptography] Bitcoin is a disaster.**
*On Tue, 2020-12-29 at 16:36 +0000, Deryk Makgill wrote: > On Monday, December 28, 2020 7:07 PM, Ray Dillinger >> >…* www.metzdowd.com](https://www.metzdowd.com/pipermail/cryptography/2020-December/036530.html)

Ray Dillinger reviewed Satoshi Nakamoto’s code and [wrote in 2017](https://www.linkedin.com/pulse/id-known-what-we-were-starting-ray-dillinger/) about his major misgivings about the current state of both Bitcoin’s culture and failures: *“I hate to even imagine how many billions of dollars of scams and failures and thefts have been perpetrated by abusing people’s faith in and enthusiasm for that technology by now.”* In the above post, he [responds](https://www.metzdowd.com/pipermail/cryptography/2020-December/036530.html) to a question about the blocksize debate. This is a bit long but I think the detail is important as it sums up the previous few years in the above timeline:

>
> <em>You said on BitcoinTalk several years ago that the plan was always to</em>
> <em>raise the blocksize. Is it still your opinion that it should have</em>
> <em>been done? Or do you think that even Satoshi's original plans were</em>
> <em>flawed too?</em>

Yes, the plan was to raise the size of the blocks. And yes, I think it should have been done. The 1MB limit was considered temporary. We got the current limit just to prevent people from filling space with dumb stuff but thought, of course they'll make it bigger when people actually need the space for legit transactions. But now they can't make it bigger, because that was a classic case of nerds making a design mistake by failing to note that we were leaving a decision in the hands of people with perverse incentives. The reason that issue became the screaming sewer knife fight it became is because of toll trolls. Miners have a financial stake in the blocks continuing to be small, because bidding goes higher for a smaller amount of block space. So they hired a bunch of trolls to sabotage all discussion about raising the limit. All they have to do to kill a raised limit is refuse to mine on larger- size blocks. But that would mean abandoning all pretense of not being a cartel. The trolls and screaming you've seen are just symptoms of their need to keep the user base conflicted and uncertain. That way they don't have to alienate the community by being tremendously obvious in a highly visible 51% attack when they participate with each other in refusing a protocol with bigger blocks. The current 1MB limit was added to the code at the last minute, because Hal was concerned about the size of the block chain (and time/cost of downloading it to set up a new node) growing faster than the Internet communications bandwidth. Satoshi was confident that it wouldn't grow beyond the power of a $mumble-priced hard drive to contain as hard drives got bigger/cheaper, but that's a different thing. Hal saw a scalability problem w/r/t internet bandwidth because while drive space was on an exponential curve, internet bandwidth wasn't. And isn't. My input to the bandwidth discussion didn't go much beyond "well, of course the bandwidth would be a crippling issue at scale, but you don't need to worry about this for a small experiment .... wait, are you serious?"

### Coming to a Conclusion

I can’t claim to know whether Bitcoin will ever get larger block sizes through a hard fork, but inaction will lead to the following problems:

1. Unusable Wallets: Users with balances below the minimum fee will essentially lose their Bitcoin since the amount is unspendable. Many users use day-to-day wallets with smaller amounts, and have larger amounts locked in cold storage.
2. Merchants and platforms will increasingly adopt and accept currencies with lower fees. Bitcoin Cash, Monero, Zcash, Dash and Litecoin are all fulfilling the role Bitcoin excelled at when the block size limit was not being hit. Projects like [Raiblocks](https://raiblocks.net/), [Hashgraph](http://hashgraph.com), and [MaidSafe](https://medium.com/@danielmorgan/why-the-safe-network-matters-76ada175d26) are making the whole idea of limits, and the [ecological of impact](http://grist.org/article/bitcoin-could-cost-us-our-clean-energy-future/) of hashpower ridiculous. Bitcoin Cash is especially easy for merchants to drop in to replace Bitcoin because implementation is easy, and adoption will accelerate as transaction space remains limited.
3. Periods of high transaction volume or price decline will exacerbate the daily transaction rate limit. Price decline combined with growing transaction backlogs will reduce the mining reward and encourage miners to switch to another SHA256-compatible chain such as Bitcoin Cash. A situation some have called a ‘Chain Death Spiral’ looms in this situation. TrippySalmon runs a great site to monitor the self-interest calculations miners must make called [Fork.lol](https://fork.lol/).
4. The [current solution](https://blog.lightning.engineering/posts/2018/05/02/lightning-ux.html) for low, or fee-free transactions is the Lightning network, which itself depends on on-chain transaction to ‘enter a channel’. If everyone adopts that network instantly and the system works as advertised, people will be sending around lightning transactions, and rarely touching the Bitcoin network, only occasionally ‘settling’. Will this be Bitcoin? The number of merchants accepting Bitcoin decreases each day, while other cryptocurrencies which validate the state of the network through normal mining are cheaper and normal people can use. Unless Bitcoin receives a Block size increase, the fees for this onramp will be too high, and processors like Coinbase will lead the way in microtransactions in the Bitcoin network by encouraging commerce between user wallets for no fee.

Personally I’m absolutely exhausted by the arguments against a block size increase. What excites me is the [reinvigoration of the Bitcoin experiment](https://www.reddit.com/r/btc/comments/7dtbew/bitcoin_cash_a_reflection_on_how_far_weve_come/) in the form of Bitcoin Cash, and hundreds of other blockchain projects with development teams able to push blockchain technology to new places.

What I’ve come to believe: the idea that larger block sizes is a ‘decentralization pressure’ is false. Mining nodes and non-mining nodes are performing well with 8MB block sizes (even though they are far from full). On May 15th 2018, the limit will be raised further to 32MB. [This original research](http://hackingdistributed.com/2018/01/15/decentralization-bitcoin-ethereum/) is worth reading (From Jan 2018) regarding measuring decentralization.

Below are [Bitcoin Cash nodes](https://cash.coin.dance/nodes/all) doing their thing:

![](https://cdn-images-1.medium.com/max/1600/1*7seqBZycV_-unsnLjSQwRA.png)

In December of 2017, schools already teach Bitcoin 101 courses. In a few years, students who really want to dig into what has now become the eighth largest currency might enroll in ‘Bitcoin’s Internal Politics 101', where they’ll no doubt encounter the block size debate and the dates, figures, and moments included in this timeline. Everyone (I’m including myself here) has an incomplete picture of Bitcoin, and anyone who claims to understand the correct economic, political, or technical solution to a change in Bitcoin should be immediately considered a crazy person. Taking time to understand the governance, history, and the quasi-cohesive groups that form around technical implementations will **I hope** show tomorrow’s Bitcoin developers and implementation boosters how to behave and build consensus.

![](https://cdn-images-1.medium.com/max/1600/1*cY1qQvCNtGLF51Dao3xhjg.png)

One of these digital currencies is great for sending digital cash over the Internet to writers.

* [Daniel Morgan](https://medium.com/u/81e281bbc40e) ( [twitter](https://twitter.com/danielmorgan) )