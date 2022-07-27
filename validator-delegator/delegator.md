# 委托人

成为 BitTorrent-chain 的委托人没有先决条件。您所要做的就是拥有一个TRON帐户。

委托人无需托管完整节点即可参与验证。他们可以将BTT代币投票给验证人，并获得部分奖励作为交换。因为他们与验证人共享奖励，所以委托人也分担了风险。委托人在系统中起着至关重要的作用，因为他们可以根据自己的意愿选择验证人。

## 投票相关合约接口说明
### 为验证人投票
* 合约方法：ValidatorShare:buyVoucher(uint256, uint256)
* 参数：
    * _amount：投票数量
    * _minSharesToMint：可接受的最少份额币数量，委托人为验证人投票的BTT会转化为份额币，以表示用户为验证人所投票数占总票数的份额。委托人可通过验证人的ValidatorShare合约的balanceOf方法来查询他所拥有的份额币数量。
* 说明：
    1. 在调用buyVoucher方法之前，需要先调用[`BTT`](https://tronscan.org/#/contract/TAFjULxiVgT4qWk6UZwjqwZXTSaGaqnVp4/code)的approve方法授权大于投票数量的BTT给[`StakeManagerProxy`](https://tronscan.org/#/contract/TEpjT8xbAe3FPCPFziqFfEjLVXaw9NbGXj/code)合约。
    2. 每一个验证人都有对应的ValidatorShare合约， 可以访问StakeManagerProxy的validators[validatorId].contractAddress来获取某一个验证人对应的ValidatorShare合约地址
    3. 此方法也可为验证人追加投票


### 领取奖励
* 合约方法：ValidatorShare:withdrawRewards()
* 参数：无
* 说明
    1. 委托人调用验证人的ValidatorShare合约的withdrawRewards方法来为提取奖励，执行成功后奖励立刻到达委托人账户。

### 取消投票
* 合约方法：ValidatorShare:sellVoucher_new:(uint256, uint256)
* 参数：
    * uint256 claimAmount：取消投票的BTT数量；委托人为验证人投票的总BTT数量，可通过ValidatorShare:getTotalStake方法获取。
    * uint256 maximumSharesToBurn：可接受燃烧的最大份额币数量；委托人所拥有的份额币数量可通过ValidatorShare:balanceOf方法获取。
* 说明
    1. 取消投票可以分多次进行，但是每次之间至少间隔1个检查点。
    2. 取消投票后，质押金BTT需要经过80个检查点的锁定期，才可提取。


### 提取投票所质押的BTT
* 合约方法：ValidatorShare:unstakeClaimTokens_new(uint256) 
* 参数
    * uint256 unbondNonce：`取消投票`操作对应的nonce，即提取第nonce次`取消投票`的BTT。委托人总的取消投票次数可以通过ValidatorShare:unbondNonces方法查询。
* 说明
    1. 该方法需要在取消投票后，经过80个检查点的锁定期后，才可调用。


### 奖励复投
奖励复投是将已获得但未提取的BTT投票奖励再次投票给验证人，以获取更多的投票奖励。
* 合约方法：ValidatorShare:reStake()
* 参数：无


### 转移投票
转移投票是转移一部分票数给另一个验证人。
* 合约方法：StakeManagerProxy:migrateDelegation(uint256, uint256, uint256)
* 参数
    * uint256 fromValidatorId：源validator id
    * uint256 toValidatorId：目标validator id
    * uint256 amount：转移的BTT数量
* 说明
    1. 只能转移给validatorID 大于7的验证人
    2. 转移投票会自动触发领取奖励操作
