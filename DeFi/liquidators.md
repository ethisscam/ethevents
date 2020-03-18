## Compound

以下两段问答摘抄自 https://medium.com/compound-finance/faq-1a2636713b69
- How does liquidation work?
If the aggregate value of your outstanding borrowing is greater than your Borrow Limit, your account will be liquidated.
If your account is in liquidation (because your collateral assets decline in value, or the price of assets you’ve borrowed increases), a member of the community can repay up to 50% of your outstanding borrowed assets.
The liquidating user receives a proportionate amount of your collateral, at a 8.0% discount, as a reward.
- 清算怎样进行的？
如果你所欠外债的累计价值超过你能借的上限，你的账户资产将被清算。
如果你的账户处于清算状态（因为你的抵押资产价值减少，或者你借的资产价值增加），社区成员可以偿付高达你外债的50%。而清算者会收到你的一部分抵押品，以8%的折扣（打92折），作为奖赏。
- Can I liquidate people?
Compound offers an Account Service API that developers can use to monitor at-risk addresses, and a member of the community has built an open source liquidation dashboard.
- 我能参与清算吗？
- Compound提供了一个账户服务接口使得开发者能够使用来监测风险资产地址，有位社区成员搭建了一个开源的[清算查看面板](https://chiragkhatri.me/compound-liquidator/)。
下面是收录自官方Discord群资源频道的信息
The Compound Protocol allows users to borrow any supported asset, using cTokens as collateral. The collateralFactor of a cToken (ranging from 0% to 90%) represents the maximum portion of your collateral value that can be borrowed--if the value of your borrowing exceeds that, you will be liquidated.
创建清算机器人教程
https://blog.baowebdev.com/2019/11/how-to-build-a-compound-liquidation-bot/
