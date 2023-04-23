    BSIP: <Not Assigned>
    Title: Decentralized Finance Exchange (DFX) and Secure Oracle System 
    Authors: litepresence.com <finitestate@tutamail.com>
    Status: [ Draft ]
    Type: [ Protocol ]
    Created: 2023-04-23
    Discussion: <url>
    Worker: <Not Assigned> 

# Abstract

This BitShares Improvement Proposal aims to introduce a new oracle system and token class to BitShares decentralized exchange (DEX). This new oracle system will utilize recent advancements in blockchain technology to provide additional features, which will facilitate increased financial security and improved decentralized exchange liquidity.  

All new tokens will be sub-assets of the "Decentralized Finance Exchange" (DFX) token, such as DFX.BTC (Bitcoin), DFX.ETH (Ethereum), and DFX.USD (US Dollar). Three new token contracts will be introduced:  

### Mint and Burn

The first contract allows for "Haven Protocol" like minting and burning.  This protocol will be an alternative smartcoin mechanism to the MPA (Market Pegged Asset) on Bitshares; where no collateral maintenance is required.  The Haven contract will additionally utilize Ring Signature enhanced BitShares' "blind transfers" to provide increased privacy for transferring sub-assets.    The total supply, each users balances, the tokens that constitute that balance, and where those balances have been transferred will be zero knowledge proof stealth.  These tokens will be temporarily locked into contract when blinded in this manner.  When released from the blind state the tokens will be able to be traded on the remainder of the Bitshares DEX.   Some of the mint and burn subtokens will be eligible for cross chain swaps. 

### ACCS

The second contract will all allow atomic cross-chain swaps (ACCS) of certain sub-assets in a manner similar to Xclaim, Axelar, and Witnet Protocols. We call this "Simplex Oracle Mediated ACCS".  This second contract will enable 1:1 swaps for sub-assets that are reflective of their corresponding tokens on foreign blockchains.  Some subassets, such as DFX.GOLD will obviously have no ACCS capability as they are not reflective of the core token on a foreign chain. 

### Earning DFX

The third contract will allow for oracle data providers to earn DFX token rewards for publication services of real world off chain data.

The proposed new oracle system will include a range of features novel to Bitshares but proven on other chains to ensure security and reliability through gamification and tokenomics:

 - One Time Purchase of Oracle License with Risk of Loss
 - Bonding with Advancing Stake Period on each Publication
 - Reward and Slashing Game Theory
 - Consensus Quorum Threshold Required for Oracle Validity
 - Randomized Selection of Data Providers
 - Reputation System Based on History of Conformity
 - Decaying Initial Federated Reputation for BitShares Github Developers

### Existing Bitshares Token Interaction

Existing BitAssets and Market-Pegged-Asset (MPA) businesses, such as HONEST, will remain unchanged. These assets along with traditional Gateway User-Issued-Assets (UIA) will be allowed to compete openly with the new DFX asset class.  DFX Protocol is designed to compliment, not replace existing Bitshares Assets.   The new DFX oracle will provide a price oracle for Haven Protocol "mint and burn" style swaps, as opposed to the traditional collateralized MPA swaps. These swaps will be allowed to occur in a hidden zero-knowledge proof wallet, utilizing enhanced "blind transfer" technology on Bitshares. 

When not blind DFX core token will also be swappable for BTS core token via a special zero swap fee null account owned constant product liquidity pool where DFX swap fees will accumulate.   Also, when not blind, both DFX and DFX subtokens will be eligible to trade on books or other private pools. 

### Abstract TLDR

The proposed changes will introduce the new ability for secure atomic cross-chain swaps, implement private mint and burn smartcoin swaps, increase the privacy of blind transfers, and add a new gamified oracle system, while minimally effecting the existing Bitshares Ecosystem. 

# Motivation

## Poisoned Oracle

When a blockchain oracle becomes poisoned, it means that the data being fed into the oracle is corrupted or manipulated in some way, either intentionally or unintentionally. This can have serious consequences for the applications and systems that rely on the oracle data.

If an oracle is providing incorrect or manipulated data, it can cause applications that rely on the data to make incorrect decisions, leading to potential financial losses or other negative outcomes. For example, if an oracle provides incorrect price data for a smartcoin, it could cause traders to make trades at the wrong price, resulting in financial losses.

In addition, a poisoned oracle can also be used as a vector for attacks on the underlying blockchain. If an attacker is able to manipulate the data being fed into the oracle, they can potentially trick the blockchain into executing malicious transactions or other harmful actions.

To prevent oracle poisoning, it is important to implement robust security measures and to carefully vet the data sources used by the oracle.  In the event that an oracle does become poisoned, it is important to identify and remediate the issue as quickly as possible to minimize the impact on the system.

### Inadequacy of DPOS to Secure the Oracle

In a delegated proof-of-stake (DPoS) system like BitShares, where token holders elect "witnesses" to produce blocks and verify transactions, there is a risk that a small group of wealthy individuals could collude to manipulate the oracle for their own benefit. This is because the small number of witnesses have significant influence over the blockchain and can potentially control the data being fed into the oracle.  

If the witnesses are incentivized to act in their own self-interest rather than in the interest of the wider community, they could potentially manipulate the oracle data to their advantage. For example, they could collude to artificially inflate the price of a particular asset.   It is therefore important for the community to remain vigilant and to actively work to prevent and detect instances of oracle poisoning or other forms of manipulation.

Historically, DPOS on Bitshares has proven entirely adquate to secure the blockhain transactions.  However, DPOS has been prone to manipulation with regard to oracles.  As we can see with price history of bitCNY and other bitassets, there has been a clear tendency towards Poisoned Oracle.

### Inadequacy of Proprietary Business to Secure the Oracle

A single central authority controlling the oracle data can create significant concerns about its credibility and transparency, which can result in a loss of trust in the entire system. As in dealing with a small group of witnesses in DPOS, with centralized business there is also risk of manipulation of the data for their own benefit.   This can have a detrimental impact on the system's integrity. Therefore, users may prefer decentralized oracle solutions that rely on multiple independent sources of data and consensus mechanisms, rather than hierarchy, to ensure accuracy and security.  Decentralized solutions can provide a higher level of transparency and accountability, particularly if the data being provided is sensitive or valuable.

Moreover, when it comes to trading smartcoins, the credibility of the oracle provider becomes crucial in determining the liquidity of the token. If a single central authority cannot gain the necessary credibility, it can hinder the liquidity of the  smartcoin, limiting its trading potential in the market.

The history of HONEST branded MPAs serves as an example of the inadequacy of centralized oracle providers in generating liquidity for smartcoins. This lack of liquidity after 2 years of providing Honest Price Feeds is likely due to factors such as a lack of trust among users and the centralization of the oracle provider.  An Honest smartcoin issuer could at anytime, just like a cartel of colluding witnesses, turn dishonest corrupting everyone's investments by Poisoned Oracle.   

## High Value Centralized Gateways are Honey Pots for Exit Scams

Gateways serve as a crucial bridge for users who wish to deposit and tokenize fiat, commodities, or other cryptocurrencies into BitShares. However, if a gateway operator decides to shut down the service and withhold user funds, it can result in significant losses for users. The larger the amount of deposits with a gateway, the more tempting it may become for the operator to abscond with the funds.

To minimize the risk of such incidents, investors and users should exercise caution and perform due diligence before depositing funds with a gateway. It is essential to research the reputation of the issuer or gateway, carefully read the terms and conditions, and be mindful of the risks involved.

Although the BitShares community actively monitors and scrutinizes gateways to identify potential scams, it cannot prevent them from operating on the platform. Users should remain vigilant and be prepared to take action in case of suspicious activity or irregularities.  

Although gateway services provide an excellent short term way to get your funds onto the DEX, they do not provide an excellent long term means of preserving value in a token other than BTS.  Long term strategies which involve ongoing DEX trading vs Gateway assets, or savings held in Gateway assets, are inherently subject to ongoing Exit Scam risk.  

## Failure of Collateralized Smartcoins to Encourage Margin Loans

There are several issues with existing collateralized smartcoin technology, such as:

### Poisoned Oracle: 

BitShares MPAs face the challenge of a "poisoned oracle" - a situation where a lack of trust can lead to a reluctance to engage in transactions. Without trust, users may be hesitant to enter into MPA trades, which can hinder the growth of the ecosystem.  BitShares has implemented endless measures to tweak smartcoin fees but the risk of a "poisoned oracle" remains. It is important for the platform to continue investing in strategies that promote trust, such as improved security protocols and transparency, to foster a robust and sustainable financial ecosystem.

### High collateralization ratio: 

Current over collateralized smartcoin systems typically require a high collateralization ratio in excess of the value of the underlying smartcoin.   As a result, users need to lock up a significant amount of collateral in order to issue a smartcoin. This can be a significant barrier to entry as it wastes capital.

### Liquidation penalty: 

BitShares MPAs carry a risk of liquidation, which can result in users facing a significant penalty. The penalty charged is the difference between the amount of debt owed and the amount received from the sale of the collateral, which can result in users losing a substantial portion of their collateral.  Users should still carefully consider their risk tolerance and collateralization levels when engaging in MPA transactions. Adequate reserves should be maintained to cover any potential penalties or losses. By doing so, users can mitigate the risk of liquidation and ensure profitable and sustainable MPA transactions; but again they are wasting capital to do so. 

### Inabiltiy to Pay off Loans:

Even in the best of circumstances, it is true that in some cases, borrowers may find it difficult to exit their positions in MPAs due to low liquidity or a lack of counterparties willing to buy back their assets. This can make it challenging to repay loans or exit positions at a reasonable rate, especially in nascent low liquidity markets with few market actors.

### Price Volatility Risk:

Over collateralized smartcoins are vulnerable to price volatility risk. In the event that the price of the collateral drops significantly, the smartcoin may lose value and potentially dip below the value of the collateral, which could force the liquidation of the asset. Even though there may have been a subsequent opportunity for the user to sell at a profit, the volatility incurred by the initial drop in value may has irreparably damaged the borrower's position causing undue losses.

### Limited scalability: 

Over collateralized smartcoin systems have certain limitations, particularly in terms of scalability. One such limitation is the fact that a substantial amount of collateral must be locked up for each smartcoin issued, which can prove to be a hindrance to scalability.  This over collateralization not only imposes significant financial burdens on the user, but it also represents a waste of valuable financial resources that could otherwise be utilized more effectively. Moreover, it can limit the number of smartcoins that can be issued, which may hinder the growth and expansion of the BitShares DEX platform.


## Lack of Confidence in Oracles and Gateways is Hurting Bitshares Liquidity

The BitShares platform offers powerful decentralized trading capabilities through its DEX, with orderbook and liquidity pool protocols that are among the most advanced in the industry. However, the full potential of these protocols is yet to be realized due to a lack of trust.

The oracle is a critical component of the MPA construct, as it provides the price feed for the smartcoin. However, the lack of trust in the centralized oracle provider creates a significant barrier to entry for users, as they are unwilling to put their funds at risk without confidence in the accuracy and reliability of the price feed. This lack of trust has resulted in poor performance of the MPA construct, with low liquidity and a depressed share price of the BTS core token.

Similarly, the lack of trust in centralized gateways for UIA's has resulted in poor performance of the UIA construct. Users are hesitant to deposit funds with a gateway without confidence that they will be able to withdraw their funds when they need to. Immediately upon depositing, the wise user swaps to BTS and then chooses to no longer expose themselves to Gateway counter party risk on the longer term.   This lack of trust has resulted in low liquidity for UIA's, further depressing liquidity on the DEX and the share price of the core token.

Despite the powerful protocols and features offered by BitShares, the lack of trust in the oracle and centralized gateways is hindering the growth and adoption of the platform. To overcome this challenge, the community must work together to identify and implement more decentralized and trustworthy solutions for these critical components. Only then can the full potential of the BitShares platform be realized, and its position as a leading decentralized exchange be solidified.

# Rationale

## Status

Bitshares, once a top 20 cryptocurrency, is now struggling to maintain a place in the top 500 with a market cap of approximately $30 million. In contrast, newer blockchain platforms that have integrated secure and reliable oracles, implemented simplex cross-chain swaps, and allowed for mint and burn zero knowledge on chain swaps - have far outpaced Bitshares' growth by several orders of magnitude.

In the past, there was a belief among top investors that implementing such features would harm existing businesses, as decentralized gateways would compete with centralized ones. However, it is becoming increasingly clear that the Bitshares DEX crypto market is shrinking, with liquidity declining.  It is therefore crucial to adapt and consider where the market is headed. Implementing complimentary features that increase the security and liquidity of decentralized exchange offerings is therefore a wise strategy for Bitshares and other platforms to consider.

## Parables

### Boiling a Frog

The boiling frog parable is often used to explain how a frog placed in a pot of water will not notice the rising temperature until it's too late and will eventually be boiled to death. In a business context, this means that gradual changes or problems that are not addressed can become bigger and more significant over time, eventually leading to failure.

For example, a company may have a small issue with customer service, which goes unnoticed and unaddressed. Over time, this small issue could escalate, leading to negative reviews, lost customers, and a damaged reputation. By the time the company realizes the extent of the problem, it may be too late to fix it.

The lesson from the boiling frog parable is that it's important to pay attention to small problems and address them early, before they become bigger and more significant. Just as a frog must be aware of changes in its environment to survive, Bitshares must be aware of critical problems with client trust of its token contracts and address them early to avoid failure.

### Sharpening the Saw

Imagine you have a blunt saw and you need to cut down a big tree. You try your best to saw, but you're not making much progress. Instead of giving up, you take a break and sharpen the saw. After sharpening, you can cut the tree down faster and with less effort.  Suddenly you're able to cut lots of trees in far less time.

The "sharpen the saw" parable is often used to explain the importance of taking time to improve oneself in order to be more effective in work and life. In a business context, this means that it's important for businesses to take time to retool, in order to be more marketable and successful.

The lesson from the sharpen the saw parable is that taking time to improve Bitshares blockchain token contracts and invest new product offerings can lead to greater success. By developing novel bleeding edge protocol Bitshares can can not only stay competitive but it will create a far larger ecosystem for other on chain businesses to profit from.

### Fixing Broken Windows

The broken windows theory is often used to explain how small, seemingly insignificant problems or "broken windows" left unaddressed can lead to bigger and more significant problems. In a business context, this means that small issues left unaddressed can lead to larger problems that can harm the business.

For example, if a company has a problem with its products or services, but fails to address it, customers may become dissatisfied and tell their friends. This negative word-of-mouth can spread quickly, leading to lost sales and a damaged reputation. If the company continues to ignore the problem, it may escalate into more significant issues, such as negative media coverage or even legal action.

The lesson from the broken windows theory is that it's important for Bitshares to address the issue of Poisoned Oracle and Gateway Exit Scam, before they become bigger and more significant. By taking action early and addressing small issues, Bitshares can prevent perennial failures and maintain its reputation and success.

### The Candlemaker's Petition 

In the story, candlemakers petition the government to block out the sun because it is hurting their candlemaking business. In a business context, this can be seen as an example of companies trying to protect their interests, even if it is at the expense of their clients preferences.

For example, a company may lobby for regulations that benefit their industry or products, even if it means limiting competition or hurting consumers. This behavior can lead to a lack of innovation and reduced choice for consumers. Similarly, a company may resist new technologies or business models that threaten their existing business, rather than embracing change and innovation.  As a result consumers will eventually flee the jurisdiction and move to a more free economic condition elsewhere.

The lesson from the Candlemaker's Petition is that Bitshares stakeholders should focus on creating value for customers and society, rather than protecting their own UIA and MPA interests at the expense of loss of clientele. By embracing innovation and competition, Bitshares can create new opportunities and benefits for the entire DEX ecosystem, rather than stagnating and limiting its potential for growth and success.

### Polishing a Turd

"Polishing a turd" is an uncouth phrase that describes investing resources to improve something inherently flawed in a business context. This could be trying to make a poorly designed product work or implementing an unsuitable business model. It's important to recognize flaws early on and take action rather than wasting time and resources on something that won't work.  Millions of dollars have been spent adjusting fee structures to make MPA's appealing:  Time and time again these investments have failed to change the trajectory of the chain marketcap.  It has become clear that, although the existing MPA and UIA constructs have their place on Bitshares in niche markets, users refuse to rely on them for day to day trading.  As a result, DEX liquidity is struggling and investors that remain resort to anxiously holding core BTS token as a safe refuge from counter party risk. 

### Conclusions

Bitshares is falling in rank among the greater crypto ecosystem.  It is relying on 10 year old collateralized smart coin technology and gateways prone to exit scams.   Users have been and are continuing to flee.   We cannot continue to ignore the broken windows.  We cannot let the frog slowly boil expecting one day it will magically free itself.   Polishing old turds with millions of dollars of incremental changes is not the path to success.  Nor is petitioning the committee to outlaw new technology.   The time has come to sharpen our saw and offer a more valuable product that will catalyze a rebirth of Bitshares blockchain.   

# Specifications

## The Oracle System Can Be Improved

New features can provide a robust system of checks and balances to mitigate the risk of oracle poisoning and ensure the integrity of the system.  While Bitshares has lagged behind in oracle technology several other blockhains have paved roads in this field setting the stage for a robust and secure implementation on our chain.   By looking at many chains that have worked on Oracles in the past 10 years we can learn from their success and failures to build our own securely gamified Oracle system.  DFX protocol will implement the following oracle improvements towards that end: 

### One Time Purchase of Oracle License with Risk of Loss: 

This requires a significant upfront cost to acquire an oracle license, which acts as a barrier to entry for bad actors looking to exploit the system for short-term gain. Additionally, a system will be put in place to allow licensed oracle providers to ban one of their own through quorum consensus. This risk of loss provides added incentive for honest actors to ensure the system remains secure and functional.  For honest providers this provides a mechanism to protect the integrity of the oracle.  For dishonest exploiters this adds expense to any attack for short term gain. 

### Staked Bond with Advancing Bond Period on each Publication: 

Oracle providers will be required to stake a bond to participate in the system, which acts as a form of collateral.  Every time the data provider publishes their Bond stake period is reset into the future.   The advancing bond period also incentivizes oracle providers to provide legitimate data that does not adversely effect the value of their staked bond in the future when they can access it again for sale.   

### Rewards and Slashing Game Theory: 

This provides a system of rewards and penalties that incentivizes oracle providers to behave honestly and provide accurate data.  Their collateral bond is at risk.   If an oracle provider is found to be malicious or provides inaccurate data, their bond is slashed, which serves as a penalty. However, if the bonded oracle provider is first to provide data and his response matches the consenus he will receive a reward, paid in newly minted DFX tokens.  DFX rewards will be subject to an inflation curve similar to bitcoin.  

### Consensus Quorum Threshold Required for Valid Oracle: 

This requires a certain number of oracle providers to provide a datum in order for it to be considered valid. This provides a form of checks and balances to prevent any one oracle or small number of providers from manipulating the system.

### Randomized Selection of Data Providers: 

Random selection ensures that no one oracle provider has too much power or influence over the system. Data providers are chosen randomly from a pool of eligible candidates, which helps to prevent any one entity from gaining too much control.  This selection can also be weighed based licensed provider reputation.

### Reputation System Based on History of Conformity: 

This provides a way to track the behavior of oracle providers over time. Providers who consistently provide accurate data and behave honestly are rewarded with a good reputation, while those who behave maliciously or provide inaccurate data are penalized with a bad reputation.   This reputation can then be used when choosing which random providers are selected to be included in each round of datum collection in a weighted fashion.   The reputation system will work on a rolling average over time. 

### Decaying Initial Federated Reputation for BitShares Github Developers: 

Initially no oracle provider has any reputation and nobody has a license to provide oracle services.   By tying Bitshares Github contributors to specific Bitshares accounts we can create an initial pool of eligible reputable licensed data providers with baseline reputation.   This ensures we have a pool of providers at the onset.   However this decaying reputation makes sure that even trusted individuals with initial access to the system are subject to ongoing scrutiny and accountability. The initial trust given to these individuals decays over time, requiring them to continue to behave honestly and responsibly in order to earn their reputation and access to the system.  It is suggested that anyone that has contributed to github/bitshares repositories in the past 2 years be granted an initial federated oracle license.  

## Haven Protocol is Simpler and More Effective than Collateralized MPA's

When a user wants to convert their DFX tokens into DFX.USD subtokens, they send their DFX tokens to a special smart contract address, which mints an equivalent amount of DFX.USD subtokens and burns the DFX tokens. These "mint and burn" operations will be designed to leave no sense of total supply or individual user balances; Zero Knowledge.   In this way they will be unique from "issue and reserve" primitives already on chain. 

This process is controlled by an oracle just like MPA.  However, no collateral is required.  Whatever the DFX is worth, the user will receive immediately in DFX.USD (subject to Protocol Fees).   Once the DFX tokens are burned, the smart contract mints an equivalent amount of DFX.USD subtokens to the user's wallet address.  There is no ongoing collateral requirement and risk to a "borrower" of a margin loan. 

Conversely, when a user wants to convert their DFX.USD subtokens back to DFX tokens, they send their DFX.USD subtokens to the DFX Protocol smart contract. The smart contract then burns the DFX.USD subtokens and mints the equivalent amount of DFX tokens to the user's wallet address.

The "mint and burn" primitives will be used to swap between other DFX subtokens that represent core tokens on foreign chains such as DFX.BTC (Bitcoin) DFX.ETH (Ethereum) or fiats such as DFX.USD or precious metals such as DFX.GOLD.   

The protocol will primarily focus on top tier cryptos, precious metals, and world class fiats.  In general, only tokens for which reliable oracles can be generated.  HONEST brand serves as a good starting point to discuss which tokens should be eligible and also provides free open source price feed scripts to utilize for this purpose.

### Haven Protocol is Private

Haven Protocol uses ring signatures to enhance the privacy of transactions on its blockchain, and the ring signature scheme used by DFX will follows a similar premise to the linkable ring signature scheme: 

Upon transfer of DFX and DFX subtokens held in a blind balance, DFX will use a specific type of ring signature called "CLSAG" (Compact Linkable Spontaneous Anonymous Group), which was developed to improve the efficiency and security of linkable ring signatures. CLSAG improves the efficiency of the signature verification process and reduces the size of the signature itself. This makes it more practical to implement ring signatures in a blockchain context.

Ring signatures are a cryptographic tool that can be used to enhance the privacy of blockchain transactions. In a typical digital signature scheme, a sender signs a message using their private key, and anyone with access to the public key can verify that the signature is valid. However, in a ring signature scheme, a group of users each have a public key, and any one of them can sign a message on behalf of the group, without revealing which member of the group actually signed it. This creates a degree of anonymity for the signer and enhances privacy. In the context of blockchain transactions, ring signatures are used to hide the identity of the sender by allowing them to sign a transaction using a group of public keys, rather than their own. This makes it difficult for anyone observing the transaction to determine the actual sender. 

Along with improving existing blind balances with Ring Signatures the feature that allows DFX Protocol to create privacy for users are Blind Swaps which add entropy to the system.

### Arbitrage Attack

In the naive Haven 1.0 protocol, a trader could exploit the arbitrage opportunity by executing the following steps:

1) The trader would first purchase XHV on an exchange that has a lower price than the 24-hour moving average (24h MA) on the Haven protocol.

2) The trader would then convert the XHV into xUSD on the Haven protocol using a mint transaction, which would be executed at the 24h MA price.

3) Next, the trader would sell the xUSD on a different exchange that has a higher price than the 24h MA on the Haven protocol.

4) Finally, the trader would convert the received funds from the sale back into XHV using a burn transaction, which would again be executed at the 24h MA price.

The haven mainnet protocol has evolved through several iterations and has shown there are different ways to mitigate this attack; namely thoughtful implementation of staking, fees, and moving averages.  Integrating the protocol to Bitshares Decentralized exchange adds some twists to the mitigation requirements.

Its important to note that Haven Protocol is designed to be private means to preserve wealth.  Swapping through the protocol is designed to be more expensive as the user is impatient to mitigate arbitrage attack.  That does not mean that swapping DFX subtokens on Bitshares Orderbooks or Liquidity Pools will be any slower or more expensive.  The time restrictions are only when performing a DFX protocol transaction when in a blind state; or attempting to exit the blind state.  

### Gamified Arbitrage Attack Mitigation

1) Blind Balance Vesting

The first step of the DFX Protocol Arbitrage Attack Mitigation involves users entering a blind balance when utilizing the DFX swap and transfer protocol. This blind balance functions as a concealed balance that is invisible to other network users. Upon entering the blind state with DFX or its subtokens, the user's funds are vested for roughly 12 hours, during which they are unable to exit the blind state. While blinded, the user cannot access any of the existing features of the Bitshares Decentralized Exchange, such as Orderbooks.

Despite being blind, the user can still leverage the DFX protocol by swapping and transferring blind tokens without disclosing the quantity of tokens held. It is worth noting that each time the tokens are swapped or transferred within the protocol, the exit vesting time remaining resets. In order to return to a non-blinded account balance, the exit vesting time must elapse. This feature makes it difficult for arbitrageurs to exploit token prices.

Once a user's balance is in a conventional account, and they are no longer in the blind state, they can utilize all of the existing protocols on the platform, including order book fills and liquidity pool swaps.   While conventional Account balances of DFX and DFX subtokens are known, the amounts held in blind balances will be entirely private.  These tokens can be swapped for any other DFX Protocol token or transferred to any other blind balance, without public knowledge of when or what account, amount, or token was involved.   

2) Future Price Contract

DFX Protocol will treat each "mint and burn" swap as a futures contract that empowers users with a limit order right to exchange at the future oracle rate, which is set one hour ahead of the current oracle rate.

In this context, users can place a kill or fill order for a specific token exchange rate that may be fulfilled one hour into the future. The swap takes place at the oracle rate only if it is more favorable than the limit order rate requested. There is a 60-minute window during which the order may be canceled but cannot be fulfilled. If the user decides to cancel and update the order, the 60-minute period resets.

By implementing the future contract feature, users can hedge against potential price fluctuations within the protocol while the protocol mitigates arbitrage attacks. It becomes more challenging for attackers to profit from immediate price discrepancies as short-term swap staking is required. The user's 12-hour exit vesting period only resets if the mint and burn request fills.

3) Auto Scaling Fee

DFX protocol fees must always be paid in DFX core token.

Each swap conducted through the DFX protocol is subject to a fee calculated based on a simulated swap of the DFX:BTS liquidity pool. In addition to the user's requested volume in DFX terms, the calculation size is increased by the total DFX protocol swap volume recorded in the past hour. The fee is determined by dividing the pool price at the present moment by the pool price if the running hour of swap volume had occurred in a single swap transaction. 

This discount rate will be applied to the DFX swap fees, thereby increasing or decreasing the cost of using the DFX protocol as the volume changes over time. As a result, transaction fee auto scaling in the protocol is determined by the size of the DFX:BTS pool, which is a critical component of the protocol's Oracle.

4) BTS-Based Oracle

The DFX Protocol relies on an external price feed oracle to obtain accurate pricing information for foreign chains, fiats, and metals, which is measured in BTS (BitShares) terms and updated on an hourly basis. Initially, we have established on-chain oracle rates in BTS terms for BTS:BTC through centralized exchange data providers. At present, DFX is not traded elsewhere at a significant volume.

The price feed Oracle for foreign denominations is updated hourly in BTS terms and subsequently converted to DFX terms using the on-chain DFX:BTS oracle. This approach guarantees the accuracy and timeliness of the DFX subtoken price feed oracle, thereby mitigating the potential for arbitrageurs to exploit pricing discrepancies. Nonetheless, this process necessitates a reliable on-chain DFX:BTS Price Oracle.

5) DFX:BTS On Chain Oracle

DFX Protocol will establish an on-chain DFX:BTS price oracle through a liquidity pool mechanism, based on the traditional X*Y=K formula. This pool will be solely designated for this purpose.  The volume-weighted average of the past hour's (1200 blocks) swap volume will determine the liquidity pool between BTS and DFX. This ensures that the DFX:BTS price oracle remains accurate and up-to-date, reducing the potential for arbitrageurs to exploit price discrepancies by creating induced volatility.

By utilizing an on-chain calculation method for the DFX:BTS price oracle, the DFX protocol can promote transparency and reduce the risks associated with price manipulation and arbitrage attacks. Furthermore, as the pool becomes funded through fees, it will become increasingly difficult to manipulate, thus ensuring the long-term stability of the DFX ecosystem.

6) DFX:BTS Pool Funded by Fees

Following every swap executed on the DFX mint and burn protocol, a fee will be levied.  The fee will be relative to the size of the DFX:BTS pool and the total volume of the DFX swaps during the previous hour, including the current swap (see 3 above). 

During each hourly maintenance period, the fee proceeds will be utilized. Half of the fee proceeds (in DFX token) from these swaps will be positioned on the Bitshares DEX Orderbooks as a limit order at the present DFX:BTS Liquidity Pool Price. Upon maintenance, any BTS held by the protocol will be combined with matching DFX to procure DFX:BTS constant product K shares in the designated DFX:BTS pool. The K shares will then be removed from circulation by "burning to null Account".

Through this mechanism, DFX is injected into pools and immobilized, thus reducing its circulation and countering any potential mining activities. Likewise, the BTS core token will experience deflationary pressure as it is locked into the DFX:BTS pool.  Finally, users will have a steady supply of DFX on the open order books to purchase in order to pay DFX fees themselves and participate in Protocol.

7) Permitting DFX:BTS Order Books and Private Pools with Varying Fee Rates to Compete:

In addition to the designated liquidity pool, where fees accrue, the DFX protocol permits the free exchange of DFX and DFX.xxx sub-tokens through any existing medium, provided such transactions are not obscured. This allowance enables price discovery, enhances user liquidity, neutralizes delta, and confers upon DFX sub-tokens fungibility as smartcoins within the open market.

8) Inverse tokens of every DFX sub-token through the DFX protocol swaps:

As a means of bolstering market efficiency, the DFX protocol will facilitate the creation of complementary inverse tokens for every DFX sub-token. For instance, the DFX.USD sub-token will be accompanied by a complementary inverse token named DFX.USDSHORT, which will be issued at a value of 1/price feed of DFX.USD. This approach serves as a delta neutralization measure for bullish and bearish market conditions, as it ensures that there is equal demand for DFX in either scenario.

By enabling inverse tokens, the DFX protocol provides traders with additional hedging opportunities while simultaneously making it more difficult for arbitrageurs to exploit the Protocol upon shift in market trend. This increased market efficiency has the potential to improve overall trading outcomes and reduce systemic risks.

9) Determining Required Blocks for System Protection by Oracle Data Providers:

Oracle data providers signal the necessary number of blocks needed to protect the system from attack. The median of valid oracle responses within the past day is utilized to compute various parameters, including:

- period to calculate the DFX:BTS price oracle moving average (hour)
- duration of futures contract for swaps (hour)
- period for cumulative volume to calculate fees (hour)
- vesting balance blocks to enter and exit the blind state (half day)

In the absence of this feature, a hardcoded reasonable number of blocks, such as 1200 blocks, may be utilized for hourly moving average periods. However, employing a voting-based approach enhances the system's stability and mitigates any potential attack vectors as they arise.

## Axelar, Xclaim, and Witnet have proven Simplex Oracle Mediated ACCS

An oracle mediated atomic cross chain swap is a decentralized process that allows users to exchange assets between different blockchain networks. Oracles, which are trusted data sources, provide information about the assets being swapped, and smart contracts execute the swap once the conditions are met. This process enables secure, trustless, and seamless transactions between different blockchain networks without relying on centralized intermediaries.

In a traditional Hash Time Lock Contract (HTLC) cross chain swap, the smart contracts on each blockchain network (duplex communication) interact with each other to execute the swap. However, in an Simplex Oracle Mediated Atomic Cross Chain Swaps (SOMACCS), the smart contract executes on one blockchain network.  Relative to HTLC, this simplifies the process, reduces the complexity of the swap, and allows for swaps to chains that do not natively support smart contracts.  Further developers are not required to write new smart contracts on each new foreign chain's native language.  All smart contracting is done once on Bitshares for all foreign chains to be compatible. 

Axelar, Xclaim, and Witnet have revolutionized the world of blockchain technology by demonstrating that SOMACCS can create decentralized gateways. With these cutting-edge solutions, blockchain networks can communicate with each other seamlessly, enabling secure and reliable transactions across multiple chains. These game-changing advancements have opened up new possibilities for decentralized finance, empowering users to trade digital assets without the need for centralized intermediaries. By leveraging the power of SOMACCS, the chain can benefits from easier integration with foreign chains, more efficient transactions, and enhanced security. 

Here's a flowchart that explains how Axelar, Xclaim, and Witnet achieve decentralized gateways using SOMACCS:

### Initiate a swap: 

Alice initiates a swap request by sending a message to the decentralized finance exchange gateway smart contract (SOMACCS Contract).   "If Bob gives me real BTC on Bitcoin chain, I will give Bob DFX.BTC on Bitshares Chain 1 for 1."  NOTE: A potential alteration to this schema is to allow Alice to offer at an exchange rate on an order book; eg 0.95:1

### Validate the request: 

SOMACCS Contract validates the request and confirms that Alice has sufficient DFX.BTC for the transaction.  It also validates Alice's BTC address on Bitcoin blockchain.  

### Parties agree to a smart contract: 

Bob sees Alice's offer on Bitshares and agrees to her terms.   Bob will be required to HTLC a small griefing fee, subject to loss to Alice if he wastes her time.    SOMACCS Contract HTLC's Alices's funds and generates a unique hash.   

### Send the hash: 

SOMACCS Contract sends the hash to the oracle.   Bob now has a limited time to send his Bitcoin to Alice.   If he fails, Alice keeps the greifing fee and her funds are released back to her.  If he succeeds, Alice's DFX.BTC will be transferred to Bob.

### Retrieve the data: 

The oracle retrieves the data from the external blockchain and returns it to the SOMACCS Contract.

### Generate a signature: 

The SOMACCS contract generates a signature using the retrieved data and the hash.

### Verify the signature: 

The SOMACCS contract verifies the signature to ensure that the data is valid.

### Execute the transaction: 

Once the signature is verified, the real BTC is known to have moved correctly on Bitcoin blockchain, the Bitshares SOMACCS contract is executed, and the Alices's DFX.BTC is transferred to Bob.

Alternatively, if the SOMACCS contract terms time out, Bob's griefing fee will be sent to Alice for wasting her time.  Alice will keep her DFX.BTC.

### Receive the swapped assets: 

Bob no longer has BTC; it has been sent to Alice and that has been confirmed by Oracle.   Alice no longer has DFX.BTC; it has been sent to Bob executed by SOMACCS contract.

### Complete the swap: 

The swap is complete, and the user can now access their new digital assets on the desired blockchain network.

Through this process, Axelar, Xclaim, and Witnet are able to create decentralized gateways using Simplex Oracle Mediated Atomic Cross Chain Swaps, which allow for secure and efficient transactions across multiple blockchain networks without the need for centralized intermediaries.

# Discussion

This project is quite complex and multifaceted.   It pulls together themes found on multiple very successful blockchains.   The fine details of the implementation are best left to those developers actively developing and capable of contemplating sublime nuance concerns as they arise.   I believe it is important to keep our core developers engaged in the ongoing development of Bitshares protocol.  I also believe they will be inspired to work on novel protocol which builds their resumes with the creation of bleeding edge cryptographic magic rather than incremental changes to dated systems.

### Specification of Improvement

- Create a Novel Gamified Secure Oracle 
- Enable Blind Mint and Burn On Chain Swaps
- Enable Blind Ring Signature On Chain Transfers
- Enable Simplex Oracle Mediated Atomic Cross Chain Swaps
- Cause No Changes to the Existing DEX Ecosystem Products
- Adhere to spirit of principles set forth in this draft BSIP

# Summary for Shareholders

- This BSIP proposes a radically new token protocol, DFX
- DFX will compete with existing MPA, UIA, NFT, and Gateway Tokens
- DFX will introduce a secure oracle utilizing tech proven on other chains
- DFX swaps will increase entropy of existing stealth transfer primitive
- DFX transfers will include ring signatures for true privacy
- DFX will mirror the capabilities of mint and burn on Haven Blockchain
- DFX will mirror existing Simplex Oracle Mediated Cross Chain Swaps
- SOMACCS is found on billion dollar blockchains Polkadot and Axelar
- It is expected this action will greatly increase liquidity on Bitshares
- It should increased market cap and provides benefit for all
- This is not an incremental change to existing protocols
- Fiat and Metal on ramps will still be required by Centralized Gateways
- Centralized Gateways will likely also corner niche foreign chain tokens 
- bitAssets will continue to operate as witness controlled MPA's
- Propretary MPA's such as HONEST will be unaffected by the changes
- DFX ACCS protocol will target top tier crypto core tokens only
- Initially XRP, BTC, LTC, and EOS will be made available for ACCS
- These gateway procedures are open source as "BitShares Python Gateway"
- Initially 20 DFX Swap Protocol assets will be made available
- These price oracles are already open source as "Honest MPA Price Feeds" 
- Minor changes will be required to the client applications to upload feeds
- There are many sublime details which need to be thoughtfully considered
- Seasoned developers will have free range to implement details securely
- UI upgrades will be required to interact with the new protocol, a la Carte
- The estimate project cost is upwards of $350,000; subject to consultation
- The estimated build time is 9-12 months
- Proposed funding is via one time ~1% inflation of BTS monetary supply
- It is expected this 1% inflation will lead to 10X increase in market cap

# Copyright

WTFPL litepresence 2023

# See Also

XCLAIM

https://eprint.iacr.org/2018/643.pdf

https://coinmarketcap.com/currencies/polkadot-new/

AXELAR

https://axelar.network/wp-content/uploads/2021/07/axelar_whitepaper.pdf

https://coinmarketcap.com/currencies/axelar/

WITNET

https://witnet.io/witnet-whitepaper.pdf

https://coinmarketcap.com/currencies/witnet/

HAVEN

https://havenprotocol.org/app/uploads/2020/12/Haven-Protocol-White-Paper-v3-English.pdf

https://coinmarketcap.com/currencies/haven-protocol/
