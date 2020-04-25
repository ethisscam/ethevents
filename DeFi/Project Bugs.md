2020/4/25
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
