# 清算市场

目前DeFi的清算市场虽然利润丰厚，但是准入门槛很高。信息虽然透明，但是获取难度大。此外，清算市场属于典型的“三年不开张，开张吃三年”行情，只有在极端行情下才能产生丰厚收益，而且参与这个市场不仅要求懂技术，对资金体量也有要求。
## 概览
### 清算数据统计网站
- Compound/dYdX/CDP 清算统计网站(不包含Maker MCD）
https://loanscan.io/supplied-liquidity#liquidation-volume 
### 讨论清算市场的文章
- 有效前沿公司2019年11月5号发表的一篇[清算市场讨论文章](https://medium.com/efficient-frontier/decentralized-finance-liquidations-a-business-opportunity-assessment-c0eea7bdacec ) 作者写完这篇文章后下一篇文章就是宣告离开币圈（Sad),他认为这个圈子离大规模用户还很远。

这篇文章发表于2019年11月5号，回顾了过去一年DeFi清算市场状态。从文中可以看出，过去一年整个清算市场拍卖的抵押品价值5863万美元，而清算者获利212万美元。文章进行了收益与风险分析，收益主要来自参加清算获得的折扣补偿，而风险包括：

intensive capital requirements — In order to liquidate a $1m loan the liquidator needs $1m to do it.

资本需求敏感型 - 要清算价值100万的贷款清算者需要准备100万资金。

Highly periodic — Liquidations come in bursts with major market moves. On Sept 24 $8.2M was liquidated in a single day and roughly $320k in liquidation revenues were earned. (not including gas and other costs). 30 days can elapse with no significant liquidations taking place.

高周期型 - 重大市场走势（价格暴涨或暴跌）才会引发大量清算。在9月24号，一天之内清算820万美元的资产，产生32万美元的清算回报。（不含油费和其他成本）。也有可能发生30天里没什么大的清算。

Watching Loans — a monitoring system is required to watch loans that are at risk of becoming under collateralized

监控贷款 - 要求开发一个监测系统来监控那些抵押不足的风险贷款。

Watching MakerDAO Price Oracle — The ability to watch the MakerDAO price oracle (everyone using this for market prices) and predict when it will change price as well as how this flows through to the liquidation key moments is key.

监控MakerDAO价格预言机 - 要求具备能够监控MakerDAO价格预言机的能力（因为大家都用它作为市场价），预测何时价格会变化及这将会如何传导至清算关键时刻是核心技能。

Gas Prices — can erode profits can this be navigated?

Gas价格 - Gas支出会不会侵蚀收益，这能确定吗？（七哥注：要看清算资产体量，体量越小越有可能入不敷出。但是体量大对资金要求也高）

Hedging — I’ve read that hedging is part of some players strategy to offset movements in PETH, ETH and other volatile assets

对冲 - 我了解到对冲作为一些清算者的策略来平衡PETH，ETH和其他波动资产的价格移动。

Borrowing — The system may need the capability to programmatically barrow capital from the DeFi ecosystem in order to pay off loans.

借款 - 系统也许需要具备从其DeFi生态中程序化借款的功能来支付贷款。（七哥注：这好像与清算无关，除非清算者借款来参与清算）

## Compound

### 以下两段问答摘抄自 https://medium.com/compound-finance/faq-1a2636713b69
**How does liquidation work?**

If the aggregate value of your outstanding borrowing is greater than your Borrow Limit, your account will be liquidated.
If your account is in liquidation (because your collateral assets decline in value, or the price of assets you’ve borrowed increases), a member of the community can repay up to 50% of your outstanding borrowed assets.
The liquidating user receives a proportionate amount of your collateral, at a 8.0% discount, as a reward.

**清算怎样进行的？**

如果你所欠外债的累计价值超过你能借的上限，你的账户资产将被清算。
如果你的账户处于清算状态（因为你的抵押资产价值减少，或者你借的资产价值增加），社区成员可以偿付高达你外债的50%。而清算者会收到你的一部分抵押品，以8%的折扣（打92折），作为奖赏。

**Can I liquidate people?**

Compound offers an Account Service API that developers can use to monitor at-risk addresses, and a member of the community has built an open source liquidation dashboard.

**我能参与清算吗？**

Compound提供了一个账户服务接口使得开发者能够使用来监测风险资产地址，有位社区成员搭建了一个开源的[清算查看面板](https://chiragkhatri.me/compound-liquidator/)。

### 下面是收录自官方Discord群资源频道的信息

The Compound Protocol allows users to borrow any supported asset, using cTokens as collateral. The collateralFactor of a cToken (ranging from 0% to 90%) represents the maximum portion of your collateral value that can be borrowed--if the value of your borrowing exceeds that, you will be liquidated.

创建清算机器人教程

https://blog.baowebdev.com/2019/11/how-to-build-a-compound-liquidation-bot/
