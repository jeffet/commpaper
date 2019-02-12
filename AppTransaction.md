### Run transactions using the participant applications.


#### Adding the connection Profile
Before building the client application, you first need to add the connection profile to your project directory. This connection profile has the information necessary for your application to connect to the local Hyperledger Fabric network. To do this, copy the **networkConnection.yml** file from this repo into the *gateway* directories for both *magnetocorp* and *digicorp* in the commercial paper project and overwrite the existing network conenction file. 


#### Transaction 1: Execute an issue transaction as Isabella@MagnetoCorp
Change directory to MagnetoCorp’s application directory:
```
cd commercial-paper/organization/magnetocorp/application
```

Install the NodeJS application dependencies (you may get some “WARNs” in the output — you can ignore those for now):
```
npm install
```
Run the wallet import script. This will import the User1 sample cert for this Org1 user into an identity/user/isabella/wallet folder, which is located under the same sub-tree as the application folder.
```
node addToWallet.js
```
A simple message of “done” will show that the import task is complete.

Now execute the first commercial paper transaction from the application directory — the “issue” transaction:
```
node issue.js
```
You should get messages confirming it was successful:

![Issue transaction](images/IssueTransaction.png)


#### Transaction 2. Execute a buy transaction as Balaji@DigiBank
Change the directory to DigiBank’s application directory:
```
cd ../../digibank/application
```
Install the NodeJS application dependencies (you may get some “WARNs” in the output — you can ignore those for now):
```
npm install
```
Run the wallet import script. This will import the sample cert for this Org2 user into an identity/user/balaji/wallet folder, which is located under the same sub-tree as the application folder.
```
node addToWallet.js
```
A simple message of “done” will show that the import task is completed.

Now execute the “buy” commercial paper transaction from the application directory:
```
node buy.js
```
You should get messages confirming it was successful:

![Buy transaction](images/BuyTransaction.png)

[<< Prev (Setup)](Readme.md)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
[>> Next (Query world state)](Queries.md)

