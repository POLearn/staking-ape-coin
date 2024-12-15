### Claiming $APE Rewards

If you've staked your BAYC NFT and want to claim your rewards without unstaking your NFT, the process is simple. Here's how you can easily claim your ApeCoin rewards:

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_claim_method.png)

There are two methods for claiming rewards: `claimSelfBAYC` and `claimBAYC`. The key difference is in convenience: `claimSelfBAYC` allows the owner of the BAYC NFT to claim rewards directly for themselves, while `claimBAYC` enables the owner to send the claim to another recipient, offering flexibility in reward distribution.

Both methods utilize the `_claimNft` function in the ApeCoin Staking Contract. This function processes and validates the claim request for staked NFTs like BAYC (or MAYC) tokens. It begins by confirming that the caller is the legitimate owner of the NFT, ensuring that only authorized owners can claim rewards.

For each NFT in the provided list, the function calculates the rewards to be claimed using the `_claim` function, which ensures accurate reward calculation based on the pool's accumulated rewards. After processing the claim, a `ClaimRewardsNft` event is emitted, providing details about the claimed rewards and the specific NFT involved.

This function enables users to securely claim their rewards while ensuring compliance with the staking pool's rules, making it easy to retrieve earned rewards and participate in the ApeCoin ecosystem.

### Quest: Claiming Your $APE

To claim your rewards from the ApeCoin Staking Contract, simply call `claimSelfBAYC`. Since you're claiming rewards for your own BAYC, there's no need to use `claimBAYC`. Input your minted BAYC ID, noting that it's a list, as it will allow for multiple claims if desired. For example, if your BAYC ID is `31` and you want to claim for that specific BAYC, enter `[31]`.

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_claim_bayc.png)

By calling `claimSelfBAYC`, you're claiming rewards from your staked BAYC and $APE, offering an easy and efficient way to earn passive income while contributing to the growth of the ApeCoin ecosystem.

> Don’t forget to submit the transaction to Proof of Learn to mint your "I Staked a BAYC" POAP as a reward for completing this task.