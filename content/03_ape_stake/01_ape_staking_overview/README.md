### ApeCoin Staking Contract: An Interactive Guide  

The **ApeCoin Staking Contract** is the cornerstone of staking within the Ape ecosystem, enabling holders of **ApeCoin** and ecosystem NFTs like **BAYC** to earn rewards. Depending on whether you are working on the mainnet or a testnet, the contract address differs:  

| **Network** | **ApeCoin Staking Contract Address**                     |  
|-------------|----------------------------------------------------------|  
| Mainnet     | `0x5954aB967Bc958940b7EB73ee84797Dc8a2AFbb9`              |  
| Testnet     | `0x69a2e10e626a08654017075B7B0B1797ae67fe50`              |  

Connecting to the correct network is essential for interacting with the staking system. In this guide, we’ll focus on the **Testnet** to explore the contract features and operations.  

The entry point, `ApeStakeContract.sol`, powers staking functionality within the Ape ecosystem, letting users lock their assets—**BAYC NFTs** and **ApeCoin (APE)**—to earn rewards. This decentralized approach ensures transparency, security, and fair reward distribution, while actively engaging users in the ApeCoin DAO ecosystem.  

### Diving into the Staking Pools  

The contract supports four distinct pools, catering to different Ape ecosystem tokens and NFTs. Each pool is represented by a `poolId` and has its unique staking conditions:  

- **ApeCoin Pool (ID: 0)**: Exclusively for ApeCoin (ERC-20).  
- **BAYC Pool (ID: 1)**: Staking for Bored Ape Yacht Club NFTs (ERC-721).  
- **MAYC Pool (ID: 2)**: For Mutant Ape Yacht Club NFTs (ERC-721).  
- **BAKC Pool (ID: 3)**: Dedicated to Bored Ape Kennel Club NFTs (ERC-721).  

The pools are hardcoded into the contract as constants. In order to stake in the Pair pool, users should first commit a BAYC/BAKC
or a MAYC/BAKC pair.

```solidity
uint256 constant APECOIN_POOL_ID = 0;
uint256 constant BAYC_POOL_ID = 1;
uint256 constant MAYC_POOL_ID = 2;
uint256 constant BAKC_POOL_ID = 3;
```  

To retrieve information about these pools, the `getPoolsUI()` function can be called. For example, the response might look like this:  

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

The output provides key details such as the **Pool ID** (e.g., 1 for BAYC), the **Staked Amount** (e.g., 240 ApeCoins in the BAYC pool), and the **Current Time Range** for reward distribution, which includes start and end timestamps, hourly rewards (`rewardsPerHour`), and the maximum staking cap per user (`capPerPosition`). This function is a valuable tool for developers to integrate live pool stats into frontends and for users to quickly check staking limits and rewards.

### The `SingleNft` Struct: Staking NFTs Made Simple  

The **SingleNft** struct defines how NFTs are staked and withdrawn in BAYC and MAYC pools:  

```solidity
/// @dev Struct for depositing and withdrawing from the BAYC and MAYC NFT pools
struct SingleNft {
    uint32 tokenId;
    uint224 amount;
}
```  

- **tokenId (uint32):** The unique identifier for the NFT being staked, such as a specific Ape in the collection.  
- **amount (uint224):** The amount of ApeCoin staked alongside the NFT.  

This structure supports precise staking of ApeCoins with corresponding NFTs, and the use of `uint224` ensures a significant staking capacity per NFT.  

### Additional Resources  

For a deeper dive into the staking contracts and their functionality, the official ApeStake documentation is an invaluable resource:  

- [Reading Data with Ethers.js](https://docs.apestake.io/#/Reading)  
- [Understanding Global Variables](https://docs.apestake.io/#/ApeCoinStaking?id=globals)  
- [Structs Overview](https://docs.apestake.io/#/ApeCoinStaking?id=structs)  
- [Functions in Detail](https://docs.apestake.io/#/ApeCoinStaking?id=functions)  

Whether you’re building applications or exploring staking mechanics, these resources provide the knowledge needed to maximize your understanding of ApeCoin staking.