![](https://www.platformer.news/content/images/size/w2000/image/fetch/c_fill,f_jpg,q_auto:good,fl_progressive:steep,g_auto/https-3a-2f-2fbucketeer-e05bbc84-baa3-437e-9518-adb32be77984.s3.amazonaws.com-2fpublic-2fimages-2f8dfebefe-6885-44e4-bad7-f4710a5753fa_2453x588.jpg)

# 什么是 ApeCoin ($APE)？

在我们开始 Ape Staking 之前，最好先了解一下 ApeCoin (APE) 是什么。ApeCoin 是位于 APE 生态系统核心的治理和实用代币，旨在推动创新并支持 Web3 的下一次进化。它使社区能够通过艺术、游戏、娱乐和活动在元宇宙中建设和塑造文化。作为 ERC-20 代币，ApeCoin 提供了一个去中心化的协议层，用于社区主导的倡议，使持有者能够投票、创建和参与定义区块链文化未来的项目。

ApeCoin 由 **APE 基金会** 支持，且由 **ApeCoin DAO** 治理，确保透明且去中心化的决策过程。除了治理，APE 还提供访问独家游戏、活动和服务的权限，同时通过共享货币统一了生态系统。ApeCoin 的供应量上限为 10 亿个代币，旨在成为一个可持续且包容的工具，推动协作和创新。

## 合约地址

ApeCoin 合约已部署在测试网和主网，开发者和用户都可以访问：

| **网络**           | **合约地址**                                |  
|---------------------|--------------------------------------------|  
| 主网                | `0x4d224452801aced8b2f0aebe155379bb5d594381` |  
| 测试网 (Sepolia)     | `0x755457DBC2aAa7568169C58942755c8Bf2b406d1` |  

ApeCoin 在测试网和主网上的可用性为开发者和用户提供了无限的可能性，赋能他们进行实验、学习并充分利用这一创新代币的潜力。

**请注意，在本课程中进行操作时，请确保使用提供的合约地址以确保交互的准确性。有关 ApeStaking 的更多细节和文档，您可以参考官方指南 [ApeStake Docs](https://docs.apestake.io/#/README)。**

## 任务：铸造 $APE

> 现在，为了更好地理解 ApeCoin 生态系统，让我们通过测试网合约 `0x755457DBC2aAa7568169C58942755c8Bf2b406d1` 铸造 **100 M20**。

> 您可以通过在 PoL IDE 中加载合约并选择 Ethereum Sepolia 作为链来轻松加载该合约。

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_load_apecoin.png)

如果你调用合约中的 decimal 方法，返回值为 `18`，这意味着要铸造 100 $APE (M20)，你需要在钱包中铸造 `100000000000000000000`。

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_minting.png)