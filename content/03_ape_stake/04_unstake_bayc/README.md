### Withdrawing Your ApeCoin Staking Rewards

To withdraw your staked ApeCoin, you have two options: withdraw a partial amount or the full amount. Both options will automatically claim any unclaimed rewards.

**How to Withdraw:**

Now that you’ve staked your BAYC, it’s important to know how to manage your stake. If you decide to withdraw your staked ApeCoin, you can do so by calling the method `withdrawSelfBAYC` and inputting your BAYC ID and the amount of ApeCoin you wish to withdraw in the correct format `[["BAYC ID","Amount of ApeCoin to Withdraw"]]`. For example, if you have BAYC #460 and want to withdraw 10,094 ApeCoin, it will be:

```
[["460","10094000000000000000000"]]
```

Withdrawing involves transferring all or a portion of your staked amount back to your wallet. This action is available across all pools. For NFT pools, uncommitting is done by executing a withdraw with the full staked amount, which also triggers an automatic claim of any rewards.

By following these steps, you can efficiently manage your staked ApeCoin and ensure you receive your rewards while retaining control over your assets. Happy staking and enjoy your rewards!

### What's happening is happening

The `withdrawSelfBAYC` function in the ApeCoin staking contract is designed to handle the withdrawal of staked ApeCoin associated with specific NFTs. Here's a breakdown of how it works and its important aspects:

1. **Update Pool State:** The function first calls `updatePool(_poolId)` to ensure the pool's state is current.

2. **Initialization:** It initializes variables to keep track of the token ID, amount to be withdrawn, total amount to be withdrawn, and the position of each NFT in the pool.

3. **Iterating Through NFTs:** The function then iterates over the list of NFTs provided. For each NFT:
   - It retrieves the token ID and amount to be withdrawn.
   - It verifies that the caller is the owner of the NFT using the `ownerOf` function. If not, it reverts with an error.
   - It updates the position of the NFT in the pool.

4. **Claiming Rewards:** If the amount to be withdrawn is equal to the total staked amount for that NFT, it claims any unclaimed rewards using the `_claim` function and emits the `ClaimRewardsNft` event.

5. **Executing Withdrawal:** The function then performs the withdrawal by calling `_withdraw`, updates the total amount to be withdrawn, and emits the `WithdrawNft` event.

6. **Transferring Funds:** Finally, if there is any amount to be withdrawn, it transfers the total withdrawn amount to the recipient using `apeCoin.transfer`.

### Important Points for Withdrawing Stake

- **Ownership Verification:** The function checks that the caller is the owner of the NFT before proceeding with the withdrawal. This ensures that only the rightful owner can withdraw the staked amount.
  
- **Claiming Rewards:** If the withdrawal amount equals the staked amount, the function automatically claims any unclaimed rewards. This ensures users receive their earned rewards when they fully withdraw their stake.
  
- **Efficient Handling:** The function uses a loop to handle multiple NFTs in a single transaction, making the process efficient for users with multiple staked NFTs.

- **Event Emissions:** The function emits events (`ClaimRewardsNft` and `WithdrawNft`) to log important actions, making it easier to track and audit transactions on the blockchain.

### Summary

The `withdrawSelfBAYC` function is a crucial component for managing staked ApeCoin in the NFT pool. It ensures ownership verification, automatic reward claiming, and efficient handling of multiple NFTs, providing a robust mechanism for users to manage their staked assets. By understanding these key aspects, users can confidently withdraw their staked ApeCoin and maximize their rewards from the staking contract.