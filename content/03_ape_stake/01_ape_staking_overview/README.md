# ApeCoin 质押合约

**ApeCoin 质押合约** 是 Ape 生态系统中质押的基石，使 **ApeCoin** 和生态系统 NFT（如 **BAYC**）的持有者能够赚取奖励。根据你是否在主网或测试网上工作，合约地址有所不同：

| **网络**   | **ApeCoin 质押合约地址**                                    |
|------------|-----------------------------------------------------------|
| 主网       | `0x5954aB967Bc958940b7EB73ee84797Dc8a2AFbb9`              |
| 测试网     | `0x69a2e10e626a08654017075B7B0B1797ae67fe50`              |

连接到正确的网络对于与质押系统交互至关重要。在本指南中，我们将专注于 **测试网** 来探索合约的功能和操作。

入口点 `ApeStakeContract.sol` 为 Ape 生态系统中的质押功能提供支持，让用户锁定他们的资产——**BAYC NFT** 和 **ApeCoin (APE)**——以赚取奖励。该去中心化的方法确保了透明度、安全性和公平的奖励分配，同时积极地吸引用户参与 ApeCoin DAO 生态系统。

### 深入了解质押池

合约支持四个不同的池，适用于不同的 Ape 生态系统代币和 NFT。每个池都有一个 `poolId`，并具有独特的质押条件：

- **ApeCoin 池 (ID: 0)**：仅限 ApeCoin (ERC-20)。
- **BAYC 池 (ID: 1)**：用于质押 Bored Ape Yacht Club NFT (ERC-721)。
- **MAYC 池 (ID: 2)**：用于质押 Mutant Ape Yacht Club NFT (ERC-721)。
- **BAKC 池 (ID: 3)**：用于质押 Bored Ape Kennel Club NFT (ERC-721)。

这些池被硬编码为常量。为了在配对池中质押，用户应先承诺一对 BAYC/BAKC 或 MAYC/BAKC。

```solidity
uint256 constant APECOIN_POOL_ID = 0;
uint256 constant BAYC_POOL_ID = 1;
uint256 constant MAYC_POOL_ID = 2;
uint256 constant BAKC_POOL_ID = 3;
```

要检索有关这些池的信息，可以调用 `getPoolsUI()` 函数。例如，响应可能如下所示：

```json
[
   {
      "poolId": "1",
      "stakedAmount": "240000000000000000000",
      "currentTimeRange": {
         "startTimestampHour": 1734015600,
         "endTimestampHour": 1735232400,
         "rewardsPerHour": "1766604023668639053254",
         "capPerPosition": "10094000000000000000000"
      }
   },
   //...
]
```

输出提供了关键细节，如 **池 ID**（例如，BAYC 为 1）、**质押金额**（例如，BAYC 池中的 240 个 ApeCoin）以及 **当前时间范围**，包括开始和结束时间戳、每小时奖励（`rewardsPerHour`）和每个用户的最大质押上限（`capPerPosition`）。这个功能是开发者将实时池统计信息集成到前端和用户快速检查质押限额和奖励的重要工具。

### `SingleNft` 结构体：简化 NFT 质押

**SingleNft** 结构体定义了如何在 BAYC 和 MAYC 池中质押和提取 NFT：

```solidity
/// @dev 用于在 BAYC 和 MAYC NFT 池中存款和取款的结构体
struct SingleNft {
    uint32 tokenId;
    uint224 amount;
}
```

- **tokenId (uint32):** 质押的 NFT 的唯一标识符，例如集合中的某个特定 Ape。
- **amount (uint224):** 与 NFT 一起质押的 ApeCoin 数量。

此结构体支持与相应 NFT 精确配对的 ApeCoin 质押，使用 `uint224` 确保每个 NFT 有足够的质押容量。

### 额外资源

如果想更深入地了解质押合约及其功能，官方的 ApeStake 文档是一个宝贵的资源：

- [使用 Ethers.js 读取数据](https://docs.apestake.io/#/Reading)
- [了解全局变量](https://docs.apestake.io/#/ApeCoinStaking?id=globals)
- [结构体概述](https://docs.apestake.io/#/ApeCoinStaking?id=structs)
- [详细函数](https://docs.apestake.io/#/ApeCoinStaking?id=functions)

无论你是构建应用程序还是探索质押机制，这些资源提供了最大化理解 ApeCoin 质押所需的知识。