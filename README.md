# Assignment_18_Blockchain_PoA

---

## Intro 
The objective of this assignment was to explore the functionality of blockchain by setting up a private testnet. The private testnet utilizes Puppeth, Geth and a  Clique Proof of Authority algorithim. The following report will outline the various steps required to launch the test network. 

## Network Configuration

* Blocktime
* Chain ID
* Account Passwords
* Ports
* 

If you have not installed jet the Go Ethereum tool, or you have any issues, please refer to the [Unit 18 Installation Guide](../../../Supplemental/blockchain-install-guide.md) for help.

## Step 1 - Creating Nodes
Because the accounts must be approved, we will generate two new nodes with new account addresses that will serve as our pre-approved sealer addresses.

Create accounts for two nodes for the network with a separate datadir for each using geth.

./geth --datadir node1 account new
./geth --datadir node2 account new
    

![banknode1](Screenshots/banknode1.png)
![banknode2](Screenshots/banknode2.png)

## Step 2 - Genesis Blocks
* Once you have your nodes created, the next step is setting up your genesis block. 

* Open a terminal window, navigate to the `Blockchain-Tools` folder and type the following command:

 ```bash
 ./puppeth
 ```
* This should show the following prompt:

![zchain Config](Screenshots/zchain_config1.png)


* Type in a name for your network, like "zchain" and hit enter to move forward in the wizard.

* Type `2` to pick the `Configure new genesis` option, then `1` to `Create new genesis from scratch`:

Now you have the option to pick a consensus engine (algorithm) to use.

* Type `2` to choose `Clique Proof of Authority` and continue. 

*  You will also be prompted to setup your blocktime. For your blockchain we have selected 5 seconds to speed up validation time. The default time is 15 seconds. 

Next you will be prompted to setup your validation nodes:

![zchain Config](Screenshots/zchain_config2.png)

* Note - That your nodes will need to be created in order to provide the genesis block what nodes will be sealed with validation authority.
*
* Copy and paste the addresses from your nodes created in step 1 into the list of accounts to seal.  

* Paste the again in the list of accounts to pre-fund. And then choose 'no' for pre-funding the pre-compiled accounts with wei. 

* Continue with the default option for the prompt that asks `Should the precompile-addresses (0x1 .. 0xff) be pre-funded with 1 wei?` by hitting enter again,
 until you reach the `Chain ID` prompt.

* Come up with a number to use as a chain ID. In our case we used `999` and then hit enter.

You should see a success message and redirected to the original prompt:

Export genesis configurations. This will fail to create two of the files, but you only need networkname.json.

## Step 3 - Initilize Nodes


With the genesis block creation completed, we will now initialize the nodes with the genesis' json file.

Using geth, initialize each node with the new networkname.json.

./geth --datadir node1 init networkname.json
./geth --datadir node2 init networkname.json



## Step 4 - Begin Mining Blocks
* Node1
* Node2


## MyCrypto

## Transaction

* 

![Test Transaction](Screenshots/test_transaction.png)


## Summary
* 

