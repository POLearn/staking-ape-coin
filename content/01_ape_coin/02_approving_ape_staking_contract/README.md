# Approving $APE for Ape Staking

Before you can start staking your ApeCoin ($APE), it is necessary to first grant permission to the ApeCoin Staking contract. This step is crucial as it allows the staking contract to interact with your ApeCoin holdings. Without this authorization, the staking contract will be unable to move your ApeCoin into and out of the staking pools, preventing you from participating in the staking process and earning rewards.

## ApeCoin Staking Contract

To engage in ApeCoin staking, you need to interact with the correct contract depending on whether you're on the mainnet or testnet. Below are the addresses for both networks:

| Network  | ApeCoin Staking Contract Address                                |
|----------|---------------------------------------------------------------|
| Mainnet  | `0x5954aB967Bc958940b7EB73ee84797Dc8a2AFbb9`                   |
| Testnet  | `0x69a2e10e626a08654017075B7B0B1797ae67fe50`                   |

## Quest: Approving the ApeCoin Staking Contract

To start the staking process, you need to approve the ApeCoin Staking contract to spend your tokens. By calling the `approve` function on the ApeCoin Token contract (`0x755457DBC2aAa7568169C58942755c8Bf2b406d1` on the testnet), you authorize the staking contract (`0x69a2e10e626a08654017075B7B0B1797ae67fe50`) to move your ApeCoin. This step ensures that your assets are securely linked to the staking contract, giving you full access to participate in staking while maintaining control over your tokens. 

It's essential to verify that you are using the correct contract address and approve the appropriate amount, which should be `100000000000000000000` (100 $APE). Double-check everything to ensure you're authorizing the correct contract and amount before proceeding.

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_approve.png)