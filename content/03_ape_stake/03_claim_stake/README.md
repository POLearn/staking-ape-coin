### Claiming Your ApeCoin Staking Rewards

If you've staked your BAYC NFT and want to claim your rewards without unstaking your NFT, the process is straightforward. Here’s how you can easily claim your ApeCoin rewards:

#### Steps to Claim Rewards

1. **Access the Staking Contract**: Connect your wallet to the ApeCoin staking contract interface.
2. **Select the Function**: Use the function labeled `8. claimSelfBAYC` to claim your rewards for staked BAYC NFTs.
3. **Enter the NFT ID**: Input the ID of the BAYC NFT you have staked. For example, if you have BAYC #460 staked, enter `460`.
4. **Submit the Transaction**: Confirm the transaction in your wallet. This will trigger the claim process for your staking rewards.

### What's happening

To claim your staking rewards for BAYC NFTs, you’ll need to interact with the ApeCoin staking contract using the _claimNft function. Here’s a concise breakdown of the process:

Update Pool: The function begins by updating the relevant pool to ensure you are interacting with the most current data.
Verify Ownership: For each NFT in your claim list, the contract checks that you are the rightful owner of the token. If you’re not the owner, the transaction will revert.
Calculate Rewards: The function calculates the rewards associated with each NFT by invoking the _claim function, which determines the amount of ApeCoin to be claimed.
Emit Event: Once rewards are calculated, an event is emitted to notify that rewards have been claimed for the specified NFT.
By following this process, you can successfully claim your ApeCoin rewards from staking your BAYC NFTs, ensuring that you receive the benefits earned from your participation in the staking pool.

#### Benefits of Claiming Rewards

- **Retain Your Staked Amount**: By using the `claimSelfBAYC` function, you can claim your rewards without unstaking your NFT. This allows your NFT to continue earning rewards.
- **Earn Passive Income**: Regularly claiming your rewards can provide a steady stream of additional ApeCoin, maximizing the benefits of your initial stake.
- **Easy and Efficient**: The process is designed to be user-friendly, making it simple to claim rewards without navigating complex steps.

By following these steps, you can efficiently claim your ApeCoin staking rewards and continue to benefit from your staked BAYC NFTs. Happy staking and enjoy your rewards!

### Next Steps: Claiming Your Rewards

Congratulations on successfully staking your BAYC! You’re now an active participant in the ApeCoin ecosystem, contributing to its growth and reaping the benefits. Enjoy your rewards and stay engaged with the ApeCoin DAO to make the most of your staked assets. In the next step, we will go over how a staker can claim rewards.

Be sure to submit the transaction into Proof of Learn to mint an "I Staked a BAYC" Poap when finishing this resource.