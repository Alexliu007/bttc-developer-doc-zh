# 网络
BTTC的正式网从2021年12月12日起正式开始运行。同时有一个正在运行的测试网（Donau）。

## 主网

```
* 网络名称（Network Name）：BitTorrent Chain Mainnet
* Official RPC URL（RPC URL）：https://rpc.bt.io
* TronGrid RPC URL: https://bttc.trongrid.io
* 区块链ID（ChainID）：199 
* 符号（Symbol）：BTT
* 区块浏览器 1 URL（Block Explorer 1 URL）：https://scan.bt.io
* 区块浏览器 2 URL（Block Explorer 2 URL）：https://bttcscan.com/

注：主网ChainID为0xc7，十进制199。
```
 
## 测试网
BitTorrent Chain（BTTC）Donau测试网现已正式开启，目前已支持TRON测试网(Nile)，以太坊测试网(Goerli)以及BSC测试网的接入，简介如下：

| 公链  |  测试网络名称 |  URL |
| ------------ | ------------ | ------------ |
| TRON  | Nile  |  [Nile Faucet](https://testfaucet.bt.io/#/tron) |
|  ETH |  Goerli | [Goerli Faucet](https://faucet.goerli.mudit.blog/)  |
|  BSC |  BSC测试网 | [BSC Faucet](https://testnet.binance.org/faucet-smart)  |
|  BTTC | BitTorrent Chain Donau  | [Donau Faucet](https://testfaucet.bt.io/#)  |

### BTTC Donau测试网
```
* 网络名称（Network Name）：BitTorrent Chain Donau
* RPC URL（RPC URL）：https://pre-rpc.bt.io/ 
* 区块链ID（ChainID）：1029
* 符号（Symbol）：BTT
* 区块浏览器 1 URL（Block Explorer 1 URL）：https://testscan.bt.io/
* 区块浏览器 2 URL（Block Explorer 2 URL）：https://testnet.bttcscan.com/
* WebSocket：wss://pre-rpc.bt.io:8546

注：Donau测试网ChainID为0x405, 十进制1029。
```
![](https://i.imgur.com/nR1t1ZX.png)

### TRON Nile 测试网

Tron Nile测试网的接入需要使用Tronlink Chrome插件，并且Tronlink已支持Nile，用户在登录Tronlink钱包后需要切换至Nile测试网，通过水龙头申请测试币并发送至Tronlink账号，即可完成Nile测试网环境准备。
```
* Nile测试网代币申请URL：https://testfaucet.bt.io/#/tron
* Nile测试网官网地址：https://nileex.io/
* Nile测试网区块浏览器：https://nile.tronscan.org/
* Nile测试网开发资源:https://nileex.io/status/getStatusPage
```

### ETH Goerli测试网

Goerli测试网的接入需要使用Metamask，并切换至Goerli测试网，申请测试币并发送至Metamask账号，即可完成Goerli测试网环境的准备。

如Metamask还未接入Goerli测试网，需要在Metamask上添加自定义RPC网络，参数如下：

```
* 网络名称（Network Name）：Goerli - Testnet
* RPC URL（RPC URL）：https://goerli.infura.io/v3/9aa3d95b3bc440fa88ea12eaa4456161
* 链ID（ChainID）：5
* 符号（Symbol）：ETH
* 区块浏览器URL（Block Explorer URL）：https://goerli.etherscan.com
```
![](https://i.imgur.com/tBVWs5s.png)

详细操作流程可参考：[Metamask接入Goerli测试网流程](https://mudit.blog/getting-started-goerli-testnet/)。

### BSC测试网

BSC测试网的接入需要使用Metamask，并切换至Goerli测试网，通过水龙头申请测试币并发送至Metamask账号，即可完成BSC测试网环境准备。

如Metamask还未接入BSC测试网，需要在Metamask上添加自定义RPC网络，参数如下：

```
* 网络名称（Network Name）：Binace Smart Chain - Testnet
* RPC URL（RPC URL）：https://data-seed-prebsc-1-s1.binance.org:8545/
* 链ID（ChainID）：97
* 符号（Symbol）：BNB
* 区块浏览器URL（Block Explorer URL）：https://testnet.bscscan.com
```
![](https://i.imgur.com/LbnUPAH.png)

详细操作流程可参考：[Metamask接入BSC测试网流程](https://academy.binance.com/en/articles/connecting-metamask-to-binance-smart-chain)。
### JSON-RPC方法

请参考文档或使用Postman：[https://documenter.getpostman.com/view/4117254/ethereum-json-rpc/RVu7CT5J?version=latest](https://documenter.getpostman.com/view/4117254/ethereum-json-rpc/RVu7CT5J?version=latest)
