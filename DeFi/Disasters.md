## 2020/4/19
- 国内DeFi社区难忘的一天，dforce团队的DeFi借贷项目lendf.me因为imbtc的合约漏洞被黑客利用，黑客不断调用合约质押虚假制造的imbtc，然后借走所有的平台质押资产，总价值2000万刀。彼时，dforce群里、代代的defi world群，不少用户纷纷表示在平台存了很多钱，咕噜在潘帅的Maker群里提到自己质押了大几百万（不清楚是人民币还是美元）。很多用户通过向黑客地址发送交易，附加memo请求归还，言辞之恳切，处境之艰难，令人读之心伤，下面一片推文中有相关交易memo截图：
https://twitter.com/hosseeb/status/1251902348454232064

此后，不少用户发文谈自己资产被盗后的感受，包括:
*咕噜的[咕噜踩雷记](https://bihu.com/article/1923112424)*;
*橙皮书李阳的[我在DeFi里亏光又回本的两天](https://mp.weixin.qq.com/s/Wx0CyoTh5OXdOSuSn5zImg)*。

对于DeFi用户，过程是痛苦的，而结局则是令人欣慰的，因为dforce成功追回所有被盗资产。后来dforce发布[一篇文章](https://mp.weixin.qq.com/s/OhaXz_Kigz8IgtnXiFEnbg)介绍整个事件时间线，从中可以得知是新加坡警方联系黑客洗钱的dex，后来1inch发现黑客洗钱过程中暴露了自己的IP地址，进而锁定了黑客身份。在警方和项目方等重重压力下，黑客被迫归还所有盗窃资产。

## 2020/4/25
- Hegic Contract Typo, found by founders and released through [twitter](https://twitter.com/HegicOptions/status/1253937477582229505) and discord.
in a function where optionIDs should be used the founder used option.
<p> 算了，换用中文。出问题的代码路径：</p>
https://github.com/hegic/hegic-contracts-v1/blob/master/HegicOptions.sol
<p> 有问题的代码：</p>

```
 function unlock(uint[] memory optionIDs) public {
    for(uint i; i < options.length; unlock(optionIDs[i++])){}
  }
 ``` 
 这里入参是 optionIDs，但是判断数组长度的时候使用options，所以判断条件根本没生效。也就是说unlock调用不了，用户资金提取不出来。
