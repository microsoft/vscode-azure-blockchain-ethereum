# [DEPRECATED] Active at https://github.com/trufflesuite/vscode-ext   Blockchain Development Kit for Ethereum

[![Version](https://vsmarketplacebadge.apphb.com/version/AzBlockchain.azure-blockchain.svg)](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-logicapps) [![Installs](https://vsmarketplacebadge.apphb.com/installs/AzBlockchain.azure-blockchain.svg)](https://marketplace.visualstudio.com/items?itemName=AzBlockchain.azure-blockchain) [![Rating](https://vsmarketplacebadge.apphb.com/rating-star/AzBlockchain.azure-blockchain.svg)](https://marketplace.visualstudio.com/items?itemName=AzBlockchain.azure-blockchain#review-details) [![Build status](https://msazure.visualstudio.com/Blockchain/_apis/build/status/Blockchain-VS-Extensions/Blockchain-VS-Extension-Prod)](https://msazure.visualstudio.com/Blockchain/_build/latest?definitionId=71311)

The extension simplifies how you create, build and deploy smart contracts on Ethereum ledgers.

- If you are doing open source blockchain development, the extension has built in integration for open source tools such as [Truffle](https://truffleframework.com/), [Infura](https://infura.io/), and [OpenZeppelin](https://openzeppelin.com/). An Azure subscription is optional.
- If you are doing Azure development, an Azure subscription is required, log into your Azure subscription or create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin. Enjoy the same integration of open source tools with Azure Blockchain Service and other Azure hosted blockchain networks such as [Hyperledger Besu](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/consensys.hyperledger-besu-quickstart) or the enterprise supported PegaSys Plus network.

# Open Source Ethereum development

<details>
  <summary style='font-size:15pt'>Get started with smart contracts</summary>

## Create a new smart contract project

The Blockchain Developer Kit was built to work effectively for both new users to Ethereum, but not get in the way for those familiar with the process. One of the primary goals is to help users create a project structure for these smart contracts, help in the compilation and building of these assets, deployment of these assets to blockchain endpoints as well as debugging of these contracts.

One of the frameworks that the extension leverages is [Truffle Suite](https://truffleframework.com/), a well known set of tools to assist in smart contract and Dapp development. Developers that are familiar with Truffle Suite may use the Truffle command line `e.g., Truffle Init` directly from the VS Code terminal, if they like.

For developers who are not familiar with Truffle, or prefer to use the Command Palette, the extension can easily scaffold out a project directory using the following steps.

1. From the [Command Palette](https://github.com/Microsoft/vscode-azure-blockchain-ethereum/wiki/Command-Palette), type `Blockchain: New Solidity Project`

2. Select an empty directory to scaffold out your project.

3. Choose a name for your contract.

4. Press Enter.

   ![Command Palette - New Solidity Project](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/createNewProject.gif)

## Build your smart contracts

Your newly scaffolded out directory includes a simple contract and all the necessary files to build and deploy a simple, working, contract to the blockchain endpoint. Use the following steps to build your contract

1. Select your contract Solidity (.sol) file, right click and choose `Build Contracts`

   ![Right click shortcut - build contracts](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/buildContractRightClick.gif)

## Deploy to the Ethereum blockchain RPC endpoint

Once compiled, you will have your contract, contract metadata (e.g., contract ABI, bytecode) available in the smart contract .json file which will be located in the`./build directory` The next steps is to deploy these contracts to a blockchain network.

For new users, this can be hard to understand, because there are multiple steps that need to occur for the deployment to be successful. To ease this burden the extension provide a simple model to deploy to various networks. By default, this will be a local network, using Ganache. The extension will start and run an instance of ganache for the user. The options to initiate this deployment are below.

1. Select your contract Solidity (.sol) file, right click and choose `Deploy Contracts`

   ![Right click smart contract - deploy contract](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/deployContractRightClick.gif)

</details>

<br />

<details>
  <summary style='font-size:15pt'>Deploy with Truffle Ganache locally</summary>

For rapid development of smart contracts, having the ability deploy contracts to a blockchain quickly to test and debug is a key principle. One of the most popular models to achive this is using Truffle Ganache, which acts as a local blockchain/blockchain emulator to allow this quick deployment and iteration that is ideal for developers.

The extension has integrated Ganache directly into the IDE to further lower the bar to entry, and allow even faster development iteration. By default, there is nothing to configure, and the following steps can be used.

1. After selecting to deploy the contracts, either from the Command Pallette or by right clicking on the contract and selecting Deploy contracts, a dropdown will be presented with options for _where_ to deploy the contract. By default there will be a single entry on this list named development.

2. After selecting development, the IDE will create a new instance of Truffle Ganache, which will use the default configuration for the project as the target. The IDE will then deploy the contracts to this instance.

   ![Truffle default deployment](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/truffleDefaultDeploy.gif)

**OPTIONAL**: If there is a need to control this Ganache instance more or change the configuration, there are some other options that can be used that the IDE can help with as well.

1. If there is a need to run the Ganache instance on a port other than the default of 8545, a new Local Network can be created and the port configuration added for this. The steps do this are:

   a. Expand the Blockchain view in the extension by clicking the name.

   b. Next click Create a new network.

   c. Select Local Service

   d. Provide a name for this service that will be referenced when targeting it from deployment.

   e. Enter the port number to use for this local network.

   ![Custom local service](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/truffleCustomDeploy.gif)

</details>

<br />

<details>
   <summary style='font-size:15pt'>Deploy with Infura to Ethereum mainnet and testnets</summary>

If you are a developer that would like to target public testnet and mainnet for Ethereum, the ability to leverage Infura from inside the IDE is provided via this extension.

For those that aren't familiar with Infura, it provides the tools and infrastructure that allow developers to easily take their blockchain application from testing to scaled deployment - with simple, reliable access to Ethereum mainnet and testnets, and also has support for IPFS. Details can be found on the [Getting started with Infura blog](https://blog.infura.io/getting-started-with-infura-28e41844cc89/) and on the [Infura Docs pages](https://infura.io/docs).

To use Infura, the first step is to either create or connect to an existing Infura project. The IDE will step through this process.

1. Expand the Blockchain view in the extension by clicking the name.

2. Next click Create a new network.

3. Select Infura Service.

4. At this point the extension will prompt you for credentials to sign into Infura. Simply click the sign in button. Don't worry if you don't already have an Infura account, because you can create one if needed.

5. On the Infura login page, login with your Infura account credentials. If you don't already have an Infura account, simply click the Sign Up link at the bottom.

6. After signing into Infura, you will be askted for authorization to share your Infura projects with the extension. Click Authorize.

7. Next close the browser window and you will back in the IDE. A prompt will be presented to allow you to enter a project name. Enter the desired name for this.

8. Next select the availability of the project inside Infura (public or private). By default, public is the option used.

9. After a few seconds, the Blockchain view will show a new Infura Service, with your project nested under, and under this will the various endpoints that Infura provides.

10. Now that a connection to Infura has been created, this network can easily be targeted when deploying contracts. When right clicking and deploying contracts, a set of options will be added for these new Infura destinations.

11. Simply select the desired target network endpoint and the extension will deploy the contracts to this location.

![Infura deploy](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/infuraDeploy.gif)

</details>

<br />

<details>
   <summary style='font-size:15pt'>Deploy with Hyperledger Besu</summary>

Hyperledger Besu is a popular Ethereum client that is unique in that it offers a client that can be used in either public networks, such as Ethereum mainnet or private, consortium based networks. It can be deployed a variety of [ways](https://besu.hyperledger.org/en/stable/HowTo/Get-Started/Install-Binaries/), and recently a preview has been made available in [Azure](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/consensys.hyperledger-besu-quickstart?tab=Overview).

Currently, the Hyperledger Besu is fully compatible with the extension, however the provisioning of the nodes is not yet fully integrated. To connect to a running Besu node with the extension, you can do the following:

1.  Deploy Hyperledger Besu locally or in the cloud (see links in above).

2.  Retrieve the JSON rpc endpoint that will be used to communicate with the Besu network. This varies based on the deployment model, for Azure deployments these can be retrieved from the output parameters from the deployment.

3.  Update the configuration manually. This is shown in the video below. The extension has the ability to use an HD Wallet provider that simply requires a file with a mnemonic to function.

Add the following to the configuration:

```
besu: {
   network_id: "*",
   gas: 0,
   gasPrice: 0,
   provider: new HDWalletProvider(
     fs.readFileSync("<path to a file with a mnemonic>", "utf-8"),
     "<besu jsonrpc endpoint>"
   ),
 },
```

![Besu deploy](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/hyperledgerBesuDeploy.gif)

</details>

<br />

<details>
<summary style='font-size:15pt'>Deploy with Azure Blockchain Service to cloud</summary>

If you are a developer that would like to target a network that leverages Azure, this option is also available. The option to create new networks or connect to existing ones are is available, the same as with Infura and Local networks!

1. Click `-> Create a new network` in the AZURE BLOCKCHAIN tab, or type `Azure Blockchain: Create a new network` in the [Command Palette](https://github.com/Microsoft/vscode-azure-blockchain-ethereum/wiki/Command-Palette).

2. Choose your subscription, resource group and region to deploy to.

3. Enter the name of your [Consortium](https://docs.microsoft.com/azure/blockchain/service/consortium)

4. Wait until your resource has been created in Azure.
   `Note: Deploying the Azure Blockchain Service takes quite some time to complete. Please check the deployment status in the Azure portal.`

![Create and Azure Blockchain Service](https://github.com/Azure-Samples/blockchain-devkit/raw/master/media/extensionMedia/azureDeploy.gif)

</details>

<br />

## System Requirements

- Supported Operating Systems
- Windows 10
- Mac OSX
- VS Code 1.36.1 (or greater)
- Python 2.7.15
- Node 10.15.x
- Git 2.10.x

**Our [Wiki page](https://github.com/Microsoft/vscode-azure-blockchain-ethereum/wiki) includes a comprehensive getting started guide with detailed usage instructions for this plugin**

## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Telemetry

VS Code collects usage data and sends it to Microsoft to help improve our products and services. Read our [privacy statement](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409) to learn more. If you don’t wish to send usage data to Microsoft, you can set the `telemetry.enableTelemetry` setting to `false`. Learn more in our [FAQ](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

```

```
