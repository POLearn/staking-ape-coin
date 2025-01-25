# 批准 $APE 用于 Ape Staking

在您开始 staking ApeCoin ($APE) 之前，首先需要授予 ApeCoin Staking 合约权限。这个步骤至关重要，因为它允许 staking 合约与您的 ApeCoin 持有量进行交互。如果没有这一授权，staking 合约将无法将您的 ApeCoin 进出 staking 池，从而无法参与 staking 过程并获得奖励。

## ApeCoin Staking 合约

要进行 ApeCoin staking，您需要根据自己所在的网络（主网或测试网）与正确的合约进行交互。以下是两个网络的地址：

| 网络        | ApeCoin Staking 合约地址                                     |
|-------------|------------------------------------------------------------|
| 主网        | `0x5954aB967Bc958940b7EB73ee84797Dc8a2AFbb9`                |
| 测试网      | `0x69a2e10e626a08654017075B7B0B1797ae67fe50`                |

## 任务：批准 ApeCoin Staking 合约

要开始 staking 过程，您需要批准 ApeCoin Staking 合约花费您的代币。通过在 ApeCoin Token 合约 (`0x755457DBC2aAa7568169C58942755c8Bf2b406d1` 在测试网) 上调用 `approve` 函数，您授权 staking 合约 (`0x69a2e10e626a08654017075B7B0B1797ae67fe50`) 移动您的 ApeCoin。此步骤确保您的资产安全地链接到 staking 合约，使您能够完全参与 staking，同时保持对代币的控制。

务必验证您正在使用正确的合约地址并批准适当的数量，数量应为 `100000000000000000000`（100 $APE）。在继续之前，仔细检查以确保您批准了正确的合约和数量。

![](https://raw.githubusercontent.com/POLearn/staking-ape-coin/refs/heads/master/content/assets/images/ide_approve.png)