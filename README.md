## Think 2019 - Master class

### Designing and developing Blockchain networks using Hyperledger Fabric 1.4

This hands-on lab walks you through the following:

1. Setup a development environment using the IBM Blockchain Platform Extension for VS Code.
2. Develop, deploy and run smart contracts using the VS Code extension.
3. Querying world state database.
4. Build a client application using the Node.js SDK and submit transactions to the deployed smart contract.

Estimated time: <br />
This should take approximately 60 minutes to complete.

[](#setup)

### 1. Setup Fabric Development environment

(using the IBM Blockchain Platform Extension for VS Code.)<br />

#### Step 1.

Start VS Code by running the command `code` from the terminal.
IBM Blockchian extension for VS Code is preinstalled for you in this VM. Verify the installation under the Extensions view.  
![Fabric extension](images/VerifyFabricExtension.png)

Notice the IBM Blockchain platform icon on the side bar.

#### Step 2.

Start a local fabric envioronemnt.
Goto the Blockchain platfrom view and click on `local_fabric` under BLOCKCHAIN CONNECTIONS

![Starting Local Fabric](images/StartingLocalFabric.gif)

Your environment is now ready for the tutorial!

### 2. Develop, deploy and run smart contracts.

#### Step 1.

In VSCode, choose File > Open Folder, and select the contracts folder by navigating to the `$HOME/fabric-samples/commercial-paper/organization/magnetocorp/contract directory`. This is your top-level project folder for this tutorial.

#### Step 2.

Explore the `papercontract.js` file, which is located in the lib subfolder. It effectively orchestrates the logic for the different smart contract transaction functions (issue, buy, redeem, etc.), and is underpinned by essential core functions (in the sample contract) that interact with the ledger. This [link](https://hyperledger-fabric.readthedocs.io/en/master/tutorial/commercial_paper.html) explains the concepts, themes, and programmatic approach to writing contracts using the commercial paper scenario.

#### Step 3.

Open package.json and rename the contract to `papercontract`. Save the file.
![Rename Contract](images/renameContract.png)

#### Step 4.

Package the contract.
Click on the IBM Blockchain Platform sidebar icon. When you do this the first time, you may get a message that the extension is “activating” in the output pane.

Click on the `+` symbol (`Add a new package`), under the `Smart Contract packages` panel, to package up the commercial paper smart contract package for installing onto a peer. It will be called something like `papercontract@0.0.1`.

![Package Contract](images/packageContract.gif)

#### Step 5.

Install the contract.
Right click on the peer and select `Install Smart Contract`. Select `papercontract@0.0.1` from the selection list.
![Install Contract](images/installContract.gif)
Installed contract should appear as shown below:
![Installed Contract](images/installedContract.png)

#### Step 6.

Instantiate the contract
Right click on `mychannel` and select `Instantiate Smart Contract`. Select the contract `papercontract@0.0.1` from the list. When prompted for `What function do you want to call?` enter `instantiate` Note that this is case sensitive. No arguments are needed for the function.
![Instantiate Contract](images/instantiateContract.gif)
Instantiated contract should appear as shown below:
![Instantiated Contract](images/instantiatedContract.png)
Notice all the transaction methods (issue, buy, redeem).

#### Step 7.

Run an `issue` transaction.
Right click on `issue` method and select `Submit Transaction`.
Use the following data for the method arguments and do not use any spaces between arguments:

```
MagnetoCorp,00001,2020-05-31,2020-11-30,5000000
```

![Submit Issue transaction](images/submitIssue.gif)
The screenshot below shows a successful completion of `issue` transaction.
![Issued transaction](images/PaperIssued.png)

#### Step 8.

Run the `buy` transaction
Right click on the `buy` method and select `Submit Transaction`. Use the following data for the method arguments:

```
MagnetoCorp,00001,MagnetoCorp,DigiBank,4900000,2020-05-31
```

![Submit Buy transaction](images/submitBuy.gif)
The screenshot below show a successful `buy` transaction.
![Buy successful](images/PaperBought.png)

The last `redeem` transaction will be run using the Commercial Paper Loopback app.

In the next section we will learn to run indexed queries against the world state database.

[>> Next (Indexes queries)](Queries.md)
