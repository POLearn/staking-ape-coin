# 使用 $APE 质押 BAYC

将您的 **Bored Ape Yacht Club (BAYC)** NFT 与 **ApeCoin (APE)** 一起质押，是参与 ApeCoin 生态系统并赚取奖励的绝佳方式。在这个阶段，您应该已经铸造了 *100 $APE* 并在以太坊测试网上获得了 *BAYC*。现在，您已经准备好与 **ApeCoin Staking Contract** 进行交互。

![Deposit Method](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_deposit_method.png)

在 ApeCoin 生态系统中，质押 NFT 的核心功能是 **ApeCoin Staking Contract** 中的 `_depositNft` 函数。此函数允许用户将他们的 NFT（如 BAYC 或 MAYC 代币）存入质押合约。它通过验证和处理 NFT 及相关的 ApeCoin，确保质押过程的安全性。它还会更新用户的个人质押金额以及池子的总质押金额。在本例中，我们将使用 **Pool 1**。此外，它还会调整用户的 `rewardsDebt`，该值根据他们的存款追踪奖励，确保通过池子的 `accumulatedRewardsPerShare` 值准确分配奖励。

当您质押 NFT 时，存入的 ApeCoin 金额会在 `totalDeposit` 变量中累加，并触发 `DepositNft` 事件来通知交易。如果您在质押 ApeCoin，您的钱包中的总金额将转移到质押合约中，完成质押过程。此功能确保只有合法的 NFT 拥有者才能进行质押，所有质押操作都遵守池子的规则。

在这个过程中，我们使用 `SingleNFT` 结构体，它需要两个关键参数：**tokenID** 和 **amount**。在质押环境中，您将使用类似 `[["BAYC_ID", "APECOIN_AMOUNT"]]` 的结构来输入您的质押数据。

### 任务：质押一个 BAYC

要在 ApeCoin Staking Contract 中质押您的 BAYC 并开始赚取奖励，请输入您的已铸造的 BAYC ID 和您希望质押的 ApeCoin 数量，使用 `SingleNFT` 结构体。例如，如果您的 BAYC ID 是 `31`，并且您想质押 `90` $APE，结构体将如下所示：

```
[["31","90000000000000000000"]]
```

![BAYC Deposit](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_deposit_bayc.png)

一旦您提交了交易，恭喜！您已正式质押了您的 BAYC，并将一些 ApeCoin 提交到池中。通过这样做，您为 ApeCoin 生态系统的发展做出了贡献，并且现在可以开始获得奖励。

> 别忘了将交易提交到 **Proof of Learn**，以铸造您的 **"I Staked a BAYC" POAP**，作为完成此任务的奖励。