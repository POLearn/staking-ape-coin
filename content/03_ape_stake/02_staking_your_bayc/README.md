# Staking your BAYC

Staking ApeCoin with your Bored Ape Yacht Club (BAYC) NFT is a great way to participate actively in the ApeCoin ecosystem and earn rewards. Here’s a step-by-step guide on how to stake your BAYC and the benefits it brings.

## Requirements
To stake your BAYC, you will need the following:

- ApeCoin Staking Contract Address: 
    - 0x5954aB967Bc958940b7EB73ee84797Dc8a2AFbb9 (Mainnet)
    - 0x69a2e10e626a08654017075B7B0B1797ae67fe50 (Testnet)
- BAYC Tuple Format: [["BAYC ID","Amount of ApeCoin to Stake"]]

### Understanding the SingleNft Struct
The SingleNft struct is a critical component of the ApeCoin staking contract, facilitating the deposit and withdrawal of NFTs within the BAYC and MAYC pools. Here’s a closer look at what it entails:

```solidity
/// @dev Struct for depositing and withdrawing from the BAYC and MAYC NFT pools
struct SingleNft {
    uint32 tokenId;
    uint224 amount;
}
```

The `SingleNft` struct is a crucial element in the ApeCoin staking contract, facilitating the deposit and withdrawal of NFTs within the BAYC and MAYC pools. It contains two fields: **tokenId** (*uint32*), which represents the unique identifier of the NFT, corresponding to a specific Ape within the collection, and **amount** (*uint224*), which denotes the amount of ApeCoin associated with the specific NFT, allowing users to stake or withdraw a specified number of ApeCoins in conjunction with their NFT. This mean a staker can stake of max of uint224.

### How to Stake Your Minted BAYC

Now that you’ve minted your BAYC, it’s time to put it to work. By staking your BAYC with the ApeCoin Staking Contract, you can start earning rewards and actively participate in the ApeCoin ecosystem. Input your BAYC ID and the amount of ApeCoin you wish to stake in the correct format `[["BAYC ID","Amount of ApeCoin to Stake"]]. For example, having BAYC 123 and wanting to stake 10 $APE, then it'll be

```
[["123","900000000000000000000"]]
```

After that you're all set! 🎉

### What's happening

When we are calling `depositBAYC`, essentially we are calling `_depositNft` that is the implementation behind deposting the stake. It is also important to note that other Ape NFTS such as MAYC will be using the same thing. The `_depositNft` function in the ApeCoin staking contract allows users to deposit their NFTs along with a specified amount of ApeCoin for staking.

Taking a look at Line X, the flow of the contract,
- Update Pool State: The pool state is updated to reflect the latest staking information.
- Ownership Check: It verifies that the caller owns the NFT before staking.
- Amount Constraints: Ensures that the amount of ApeCoin being staked adheres to predefined rules.
- Event Logging: Logs the staking details for transparency.
- ApeCoin Transfer: Transfers the total amount of ApeCoin from the user to the contract.
This function is designed to manage and secure the staking process, ensuring only the rightful owners can stake their NFTs and that all staked amounts comply with the rules of the staking pool.

Congratulations on successfully staking your BAYC! You’re now an active participant in the ApeCoin ecosystem, contributing to its growth and reaping the benefits. Enjoy your rewards and stay engaged with the ApeCoin DAO to make the most of your staked assets. In the next step will go over how a staker can claim rewards.

To sure to submit the transaction into Proof of Learn to mint a I staked a BAYC Poap when finishing this resource.


