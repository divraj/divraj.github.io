---
layout: post
title: "Stable Asset Design and Experimentation on Ethereum"
categories: frequent
author: "Divraj Jain"

---

Capital deposited will first be temporarily stored in a hot reserve. Then at daily (hourly etc depending on gas prices ) frequency split into various assets and on-chain strategies decided by a staking inteface. Strategies can be added permissionlessly after a minimum stake is deposited by a proposer. Strategy stakers are renumerated periodically from the reserve taking into account metrics like length , size and performance of the stake. As the design is permissionless people are open to route funds to yearn vaults etc. Profits periodically transferred into a reserve pool.

<img src="https://github.com/divraj/divraj.github.io/raw/master/_assets/ethdeposit.png" width="70%">

When capital is deposited an equivalent amount of the stable asset is minted.

<img src="https://github.com/divraj/divraj.github.io/raw/master/_assets/ethwithdrawal.png" width="70%">


When there is a withdrawal if there is enough liquidity in the reserve, then the reserve is depleted and the withdrawal is made at the original locked price minus an exit fee. The exit fee is added to the reserve. The corresponding amount of stable asset are burnt from supply. 

Incase there is not enough liquidity in the reserve then withdrawals are made from strategies as to maintain the proportions. Transactions may be batched and kept in temporary reserve after modeling daily withdrawals to save gas.

Withdrawals are made in first in first out order in case of congestion and spirals.

Incase there is no capital in any of the strategies then as a measure of last resort credit tokens are minted and sent to the withdrawer. These credit tokens can be claimed in addition to compensatory interest by the withdrawer when reserve levels are sufficient.

The design may not be unique, in fact I learnt post ideation on the uncommon core podcast that YAM and others are employing similar reserve strategies to stabilize an asset. Yearn vaults also employ a similar strategy to generate yield. This design does highlight the potential of interesting projects that can arise on ethereum as modular primitives , common standards and community practices are combined and reconfigured. 

Currently building something like this design takes deep technical skill of ethereum contracts , execution , interaction (composability) , adversarial simulation / stress testing etc.. Soon tools (like Gelato) will allow quick plug and play launches further democratizing the creation of permissionless value projects. As the effort to launch such projects reduces, a projects mechanism design , financial modelling , adversarial testing and community building will become more important. Overall we will see a further rise in experimentation and quick scaling of projects on ethereum.






