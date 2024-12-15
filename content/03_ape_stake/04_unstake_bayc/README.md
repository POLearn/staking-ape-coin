### Withdrawing Your ApeCoin Staking Rewards

Say, you earn enough or simply want to unstake, you can withdraw your staked ApeCoin, by calling the method `withdrawSelfBAYC`. Withdrawing involves transferring all or a portion of your staked amount back to your wallet. This action is available across again also in MAYC or BAKC. In Ape Staking, this process is called **uncommitting** and is done by executing a withdraw with the full staked amount, which also triggers an automatic claim of any rewards.

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_withdraw_method.png)

The `withdrawSelfBAYC` function in the ApeCoin staking contract allows users to withdraw staked ApeCoin associated with their BAYC NFTs. It first updates the pool state, then checks ownership of the NFTs to ensure the caller is the rightful owner. If the full staked amount is being withdrawn, any unclaimed rewards are automatically claimed. The function then executes the withdrawal and transfers the withdrawn amount to the recipient. Events are emitted to log key actions, providing transparency. This function efficiently handles multiple NFTs in one transaction, ensuring users can easily unstake their ApeCoin while also claiming their rewards.

Similar to the *deposit* parameters, you will need to understand `SingleNFT` struct, which is in format `[["BAYC_ID", "APECOIN_AMOUNT"]]`.

### Quest: Withdrawing Your BAYC and $APE

 and inputting your BAYC ID and the amount of ApeCoin you wish to withdraw in the correct format `[["BAYC ID","Amount of ApeCoin to Withdraw"]]`. For example, if you have BAYC #460 and want to withdraw 10,094 ApeCoin, it will be:

```
[["31","90000000000000000000"]]
```

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_withdraw_bayc.png)
