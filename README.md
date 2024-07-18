# METACRAFTERS AVAX ADVANCED PROJECT 2

This project focuses on creating and managing a custom virtual machine (VM) using HyperSDK on the Avalanche blockchain platform. The goal is to implement various blockchain functionalities, including asset creation, token minting, order management, and interaction via command-line tools.

## Description

### HyperSDK and Custom Blockchain

The project includes HyperSDK, a development toolkit provided by Avalanche, to establish a custom blockchain environment. This involves defining and configuring a new blockchain network with specific parameters and capabilities tailored to the project's requirements.

### Key Components
1. Asset Creation and Management: The project enables users to create custom assets on the blockchain. This capability is crucial for defining and representing various digital and physical assets within the blockchain ecosystem.
   
2. Token Minting and Burn: It supports minting and burning tokens, which are essential operations in managing digital currencies and assets. Minting creates new tokens, while burning removes them from circulation, ensuring controlled token supply dynamics.
   
3. Order Management: The system includes functionalities for creating, filling, and closing orders on the blockchain. This allows users to trade assets and tokens according to predefined parameters, facilitating decentralized exchange operations.

4. CLI Tools and Interaction: Command-line interface tools are provided to interact with the blockchain network efficiently. These tools enable users to perform actions such as importing keys, managing blockchain configurations, and executing transactions programmatically.

   ## Project Setup

   ### Prerequisites

   Before starting, ensure you have the following prerequisites installed and configured on your system:

1. Go Programming Language: Required for building and running the HyperSDK and associated components.
2. Avalanche CLI: Needed for managing Avalanche blockchain nodes and networks.

   ## Cloning the Respository

   To set up the project locally, follow these steps:

1. Clone the Repository
2. Initialize Dependencies:
```
go mod tidy
```
Ensures all necessary Go dependencies are installed and up to date.

## Configuring Your Project

1. Define Constants: Update constants such as HRP, Name, and Symbol in consts/consts.go. These constants define essential parameters for your custom blockchain network.

2. Register Actions and Auth Methods: In registry/registry.go, ensure all required actions (e.g., asset creation, token minting) and authentication methods are registered in the HyperSDK registry. This step configures how different operations are handled within the blockchain network.

3. Build and Run Your VM: Execute the following command to build and run your custom VM locally,
```
MODE="run-single" ./scripts/run.sh
```
This command initializes your custom blockchain network with the specified configurations and prepares it for interaction.

## Using CLI tools

1. Import Demo Private Key:
   ```
   ./build/token-cli key import demo.pk
   ./build/token-cli chain import-anr
   ```
Imports the provided demo private key and configures the blockchain network accordingly for testing and development purposes.

2. Interacting with Your Custom HyperChain: Utilize the CLI tools and commands provided in the repository to interact with your custom HyperChain. These tools enable you to perform actions such as creating assets, minting tokens, managing orders, and querying blockchain state.

   ## Stopping the Local Avalanche Network

   ```
   killall avalanche-network-runner
   ```
This command terminates all processes associated with the local blockchain network.

## Mint and Trade

### Step 1: Create Your Asset

First, you'll create your own asset using the token CLI. Run the following command:
```
./build/token-cli action create-asset
```
After executing the command, the output should resemble the following:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
metadata (can be changed later): MarioCoin
continue (y/n): y
✅ txID: bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
```
 The txID provided is the assetID of your newly created asset.

 ### Step 2: Mint Your Asset
 
Once your asset is created, you can mint some of it. Use the command:
```
./build/token-cli action mint-asset
```
Upon completion, the output will look similar to this:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
assetID: bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
metadata: MarioCoin supply: 0
recipient: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
amount: 10000
continue (y/n): y
✅ txID: 2RDNc3tbUrd6PjVe6BisKAiLnaZp1ZJQG8zQMCUx83AYMNpTbZ
```
### Step 3: View Your Balance

To verify the minting process, check your balance using:
```
./build/token-cli key balance

```
The output should resemble:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
assetID: bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
metadata: MarioCoin supply: 0
recipient: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
amount: 10000
continue (y/n): y
✅ txID: 2RDNc3tbUrd6PjVe6BisKAiLnaZp1ZJQG8zQMCUx83AYMNpTbZ
```
### Step 4: Create an Order

Next, create an order on-chain using:
```
./build/token-cli action create-order

```
The output will show details of the created order:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
assetID (use TKN for native token): TKN
uri: http://127.0.0.1:37345/ext/bc/23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
balance: 999.999999119 TKN
athulyajayanv@Athulyas-MacBook-Air tokenvm-main % ./build/token-cli action create-order
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
in assetID (use TKN for native token): TKN
in tick: 1
out assetID (use TKN for native token): bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
metadata: MarioCoin supply: 10000 warp: false
balance: 10000 bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
out tick: 10
supply (must be multiple of out tick): 100
continue (y/n): y
✅ txID: jd8ZEpPhtbWP8JGtjDPKcEhuHEG24mZRuv8X3LF59sBws69iG
```
The txID is the orderID of your new order.

### Step 5: Fill Part of the Order

Fill part of the created order using:

```
./build/token-cli action fill-order

```

Upon completion, the output will provide details of the filled order:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
in assetID (use TKN for native token): TKN
balance: 999.999998631 TKN
out assetID (use TKN for native token): bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
metadata: MarioCoin supply: 10000 warp: false
available orders: 1
0) Rate(in/out): 100000000.0000 InTick: 1.000000000 TKN OutTick: 10 bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR Remaining: 100 bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
select order: 0
value (must be multiple of in tick): 2
in: 2.000000000 TKN out: 20 bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
continue (y/n): y
✅ txID: sQ6RtQJRmGhNm4i5FvK24sxLcPRQzcryDNJnQZRxmgsdaCSoT
```

### Step 6: Close Order

To cancel an order, use:

```
./build/token-cli action close-order
```
The output will confirm the closure of the order:
```
database: .token-cli
address: token1rvzhmceq997zntgvravfagsks6w0ryud3rylh4cdvayry0dl97nsjzf3yp
chainID: 23whmb5e6EFvQRRJwP8LeHFqemM79dqmDZ7mTWXTwcfU337ob
orderID: jd8ZEpPhtbWP8JGtjDPKcEhuHEG24mZRuv8X3LF59sBws69iG
out assetID (use TKN for native token): bCzyx5aQzuKKknhpnXJN3GhrgTtH112kiKdCD4rSH7vZpNkQR
continue (y/n): y
✅ txID: SYcwZf3hVKfGYe2i75qTWARim43hXvE1ghEE5H7zytQhpR9LZ
```
This command returns any funds locked in the order back to the creator's account.

## Authors

Athulya Jayan V

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
