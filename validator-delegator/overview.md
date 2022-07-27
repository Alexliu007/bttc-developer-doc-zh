# 概述

BitTorrent-Chain 是一个区块链应用平台,如果您希望通过为BitTorrent-Chain设置节点来成validator,或者希望成为委托人以将代币委托给validator并获得奖励，可以通过该文档进行快速了解相关内容。

## PoS、质押和投票

### 股权证明(PoS)

权益证明 (PoS) 是公共区块链的一类共识算法，取决于验证人在网络中的经济权益。在基于工作量证明 (PoW) 的公共区块链（例如比特币和以太坊的当前实现）中，该算法奖励解决密码难题的参与者，以验证交易并创建新块（即挖矿）。在基于 PoS 的公共区块链中，一组验证人轮流对下一个区块进行提议和投票，每个验证人投票的权重取决于其存款（即权益）的大小。PoS 的显着优势包括 安全性、降低中心化风险和能源效率。

有关更多详细信息，请参阅 [https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ)。

### 质押

Staking 是指将代币锁定到存款中以获得在区块链上验证和生产区块的权利的过程。通常，质押是在网络的本机令牌中完成的。

### 投票

投票是代币持有者将其股份委托给验证人的过程。它允许不具备运行节点的技能或愿望的代币持有者参与网络，并根据投票的股份数量按比例获得奖励。

## 架构

BitTorrent-Chain 是一个区块链应用平台，整体结构分为三层：

* Root Contracts层：TRON及其他区块链网络上的Root合约，支持用户通过存取款的方式将代币映射到 BitTorrent-Chain，及支持质押等功能。
* Validator层: 验证BitTorrent-Chain区块，定期发送Checkpoint至支持的TRON及其他区块链网络。 **Bridge**：负责监听各链路事件，发送事件消息等。 **Core**：共识模块，包括Checkpoint(BitTorrent-Chain链的状态快照)的验证，Statesync事件\&Staking事件的共识。\
  **REST-Server**：提供相关API服务。
* BitTorrent-Chain层。
