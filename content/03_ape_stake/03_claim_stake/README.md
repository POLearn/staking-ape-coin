# 领取 $APE 奖励

如果您已经质押了您的 BAYC NFT 并希望在不解锁 NFT 的情况下领取奖励，过程非常简单。以下是您如何轻松领取 ApeCoin 奖励的方法：

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_claim_method.png)

有两种领取奖励的方法：`claimSelfBAYC` 和 `claimBAYC`。它们的主要区别在于便捷性：`claimSelfBAYC` 允许 BAYC NFT 的所有者直接为自己领取奖励，而 `claimBAYC` 使所有者能够将奖励领取请求发送给其他接收者，提供了灵活的奖励分发方式。

这两种方法都使用了 **ApeCoin Staking Contract** 中的 `_claimNft` 函数。该函数处理并验证质押 NFT（如 BAYC 或 MAYC 代币）的奖励领取请求。它首先确认调用者是 NFT 的合法所有者，确保只有授权的所有者才能领取奖励。

对于提供的列表中的每个 NFT，函数使用 `_claim` 函数来计算要领取的奖励，确保根据池子累计的奖励准确计算奖励数额。在处理完领取请求后，会触发 `ClaimRewardsNft` 事件，提供关于已领取奖励和特定 NFT 的详细信息。

此功能使用户能够安全地领取奖励，同时确保遵守质押池的规则，从而使领取已赚取的奖励变得更加简单，并参与到 ApeCoin 生态系统中。

### 任务：领取您的 $APE

要从 ApeCoin Staking Contract 中领取您的奖励，只需调用 `claimSelfBAYC`。由于您是为自己的 BAYC 领取奖励，因此无需使用 `claimBAYC`。输入您的已铸造的 BAYC ID，注意它是一个列表，如果需要可以同时领取多个奖励。例如，如果您的 BAYC ID 是 `31`，并且您只想领取该特定 BAYC 的奖励，输入 `[31]`。

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_claim_bayc.png)

通过调用 `claimSelfBAYC`，您将从您的质押 BAYC 和 $APE 中领取奖励，这是一个简单高效的方式来赚取被动收入，同时为 ApeCoin 生态系统的发展做出贡献。

> 别忘了将交易提交到 **Proof of Learn**，以铸造您的 **"I Staked a BAYC" POAP**，作为完成此任务的奖励。