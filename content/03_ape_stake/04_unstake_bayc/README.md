### 提取您的 ApeCoin 质押奖励

假设您已经赚取了足够的奖励，或者仅仅想要取消质押，您可以通过调用 `withdrawSelfBAYC` 方法来提取您的质押 ApeCoin。提取包括将您所有或部分质押的金额转回到您的钱包中。此操作同样适用于 MAYC 或 BAKC。在 Ape Staking 中，此过程被称为 **解除承诺**，通过执行全额提取质押金额，同时触发自动领取任何未领取的奖励。

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_withdraw_method.png)

**ApeCoin Staking Contract** 中的 `withdrawSelfBAYC` 函数允许用户提取与其 BAYC NFTs 相关的质押 ApeCoin。该函数首先更新池状态，然后检查 NFT 的所有权，确保调用者是合法所有者。如果提取的是全额质押金额，任何未领取的奖励将被自动领取。然后该函数执行提取操作，并将提取的金额转账给接收者。此过程会触发事件，以记录关键操作，提供透明度。此函数能够在一个交易中高效处理多个 NFT，确保用户可以轻松解除 ApeCoin 质押，同时领取奖励。

与 *存款* 参数类似，您需要理解 `SingleNFT` 结构体，其格式为 `[["BAYC_ID", "APECOIN_AMOUNT"]]`。

### 任务：提取您的 BAYC 和 $APE

输入您的 BAYC ID 以及您希望提取的 ApeCoin 数量，格式为 `[["BAYC ID", "要提取的 ApeCoin 数量"]]`。例如，如果您拥有 BAYC #460，并且希望提取 10,094 ApeCoin，那么格式如下：

```
[["31","90000000000000000000"]]
```

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_withdraw_bayc.png)