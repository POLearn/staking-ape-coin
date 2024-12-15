### Staking a BAYC with $APE

Staking your Bored Ape Yacht Club (BAYC) NFT alongside ApeCoin ($APE) is a great way to engage with the ApeCoin ecosystem and earn rewards. By this point, you should have already minted *100 $APE* and acquired a *BAYC* on the Ethereum Testnet. Now, you're ready to interact with the ApeCoin Staking Contract.

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_deposit_method.png)

The core function for staking your NFTs in the ApeCoin ecosystem is the `_depositNft` function in the ApeCoin Staking Contract. This function allows users to deposit their NFTs, like BAYC tokens (or MAYC), into the staking contract. It securely handles the staking process by validating and processing the NFTs and associated ApeCoin and ensures proper security. It also will update both the user’s individual staked amount and the total staked amount for the pool. In our case it will be **pool 1**. It also adjusts the user's `rewardsDebt`, which tracks rewards based on their deposit, ensuring accurate reward attribution via the pool’s `accumulatedRewardsPerShare` value.

When you stake your NFT, the deposited ApeCoin amount is summed up in the `totalDeposit` variable, and a `DepositNft` event is triggered to notify the transaction. If you are staking ApeCoin, the total amount is transferred from your wallet to the staking contract, completing the process. This function ensures that only legitimate NFT owners can stake, and all staking actions comply with the pool’s rules.

For this process, we use the `SingleNFT` struct, which requires two key parameters: **tokenID** and **amount**. In the staking environment, you’ll use a structure like `[["BAYC_ID", "APECOIN_AMOUNT"]]` to input your staking data.

### Quest: Staking a BAYC

To stake your BAYC with the ApeCoin Staking Contract and start earning rewards, input your minted BAYC ID and the amount of ApeCoin you wish to stake in the `SingleNFT` structure. For example, if your BAYC ID is `31` and you want to stake `90` $APE, the structure would look like this:

```
[["31","90000000000000000000"]]
```

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_deposit_bayc.png)

Once you’ve submitted the transaction, congratulations! You’ve officially staked your BAYC and committed some ApeCoin to the pool. By doing this, you’ve contributed to the growth of the ApeCoin ecosystem and can now begin reaping the rewards.

> Don’t forget to submit the transaction to Proof of Learn to mint your "I Staked a BAYC" POAP as a reward for completing this task.