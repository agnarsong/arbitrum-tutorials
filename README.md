# 修改了下述内容：
## arbitrum-tutorials/node_modules/@arbitrum/sdk/dist/lib/dataEntities/networks.js
增加了l1Networks、l2Networks的网络配置
```shell
    1337: {
        blockTime: 15,
        chainID: 1337,
        explorerUrl: '',
        isCustom: false,
        name: 'arbl1',
        partnerChainIDs: [412346],
        isArbitrum: false,
    },
```

l2Networks 的数据获取：`https://developer.arbitrum.io/node-running/local-dev-node`
```shell
    412346: {
        chainID: 412346,
        confirmPeriodBlocks: 20,
        ethBridge: {
          bridge: "0x2b360a9881f21c3d7aa0ea6ca0de2a3341d4ef3c",
          inbox: "0xff4a24b22f94979e9ba5f3eb35838aa814bad6f1",
          outbox: "0x49940929c7cA9b50Ff57a01d3a92817A414E6B9B",
          rollup: "0x65a59d67da8e710ef9a01eca37f83f84aedec416",
          sequencerInbox: "0xe7362d0787b51d8c72d504803e5b1d6dcda89540"
        },
        explorerUrl: "",
        isArbitrum: true,
        isCustom: true,
        name: "ArbLocal",
        partnerChainID: 1337,
        retryableLifetimeSeconds: 604800,
        nitroGenesisBlock: 0,
        depositTimeout: 900000,
        tokenBridge: {
          l1CustomGateway: "0x3DF948c956e14175f43670407d5796b95Bb219D8",
          l1ERC20Gateway: "0x4A2bA922052bA54e29c5417bC979Daaf7D5Fe4f4",
          l1GatewayRouter: "0x525c2aBA45F66987217323E8a05EA400C65D06DC",
          l1MultiCall: "0xDB2D15a3EB70C347E0D2C2c7861cAFb946baAb48",
          l1ProxyAdmin: "0xe1080224B632A93951A7CFA33EeEa9Fd81558b5e",
          l1Weth: "0x408Da76E87511429485C32E4Ad647DD14823Fdc4",
          l1WethGateway: "0xF5FfD11A55AFD39377411Ab9856474D2a7Cb697e",
          l2CustomGateway: "0x525c2aBA45F66987217323E8a05EA400C65D06DC",
          l2ERC20Gateway: "0xe1080224B632A93951A7CFA33EeEa9Fd81558b5e",
          l2GatewayRouter: "0x1294b86822ff4976BfE136cB06CF43eC7FCF2574",
          l2Multicall: "0xDB2D15a3EB70C347E0D2C2c7861cAFb946baAb48",
          l2ProxyAdmin: "0xda52b25ddB0e3B9CC393b0690Ac62245Ac772527",
          l2Weth: "0x408Da76E87511429485C32E4Ad647DD14823Fdc4",
          l2WethGateway: "0x4A2bA922052bA54e29c5417bC979Daaf7D5Fe4f4"
        }
    }
```

## packages/token-deposit/contracts/DappToken.sol
修改精度为18
uint8 public decimals = 18;

## packages/token-deposit/scripts/exec.js
添加日志打印
console.log("l2TokenAddress: ", l2TokenAddress)

# Arbitrum Tutorials

This monorepo will help you get started with building on Arbitrum. It provides various simple demos showing and explaining how to interact with Arbitrum — deploying and using contracts directly on L2, moving Ether and tokens betweens L1 and L2, and more.

We show how you can use broadly supported Ethereum ecosystem tooling (Hardhat, Ethers-js, etc.) as well as our special [Arbitrum SDK](https://github.com/OffchainLabs/arbitrum-sdk) for convenience.

## Installation

From root directory:

```bash
yarn install
```

## What's included?

#### :white_check_mark: Basics

- 🐹 [Pet Shop DApp](./packages/demo-dapp-pet-shop/) (L2 only)
- 🗳 [Election DApp](./packages/demo-dapp-election/) (L2 only)

#### :white_check_mark: Moving Stuff around

- ⤴️ 🔹 [Deposit Ether](./packages/eth-deposit/)
- ⤵️ 🔹 [Withdraw Ether](./packages/eth-withdraw/)
- ⤴️ 💸 [Deposit Token](./packages/token-deposit/)
- ⤵️ 💸 [Withdraw token](./packages/token-withdraw/)

#### :white_check_mark: General Interop

- 🤝 [Greeter](./packages/greeter/) (L1 to L2)
- 📤 [Outbox](./packages/outbox-execute/) (L2 to L1)
- ⏰ [L1 Confirmation Checker](./packages/l1-confirmation-checker/)

#### :white_check_mark: Advanced Features

- ®️ [Arb Address Table](./packages/address-table/)
- 🌉 [Bridging Custom Token](./packages/custom-token-bridging/)
- ✈️ [Delayed inbox message(l2MSG)](./packages/delayedInbox-l2msg/)
- 🎁 [Redeem Retryable Ticket](./packages/redeem-failed-retryable/)

<p align="center"><img src="assets/logo.svg" width="300"></p>
