# Gimli Smart Contracts #

## How to Deploy ##

In order to deploy Gimli Smart Contract you need the
following software to be properly installed on your system:

1. Geth 1.6.5+ (https://geth.ethereum.org/)

Also, you need Ethereum node running on your system and synchronized with the
network.  If you do not have one, you may run it via one of the following
commands depending on whether you want to connect to PRODNET or TESTNET:

    geth
    geth --testnet

If you are running Ethereum node for the first time, you may also add "--fast"
flag to speed up initial synchronization:

    geth --fast
    geth --testnet --fast

Also you need at least one account in your node.  If you do not have any
accounts, you may create one using the following commands:

    geth attach
    > personal.newAccount ();
    > exit

It will ask you to choose passphrase and enter it twice, and it will output an
address of your new created account.

You will also need some ether on your primary account.

In order to deploy Gimli Smart Contract do the following:

1. Go to the directory containing deployment script, i.e. file named
   `GimliDeploy.js`.
2. Attach to your local Ethereum node: `geth attach`
4. Unlock your primary account:
   `personal.unlockAccount (web3.eth.accounts [0]);` (you will be
   asked for your passphrase here)
5. Run deployment script: `loadScript ("GimliDeploy.js");`
6. If everything will go fine, after several seconds you will see message like
   the following: `Deployed at ... (tx: ...)`,
   which means that your contract was deployed (message shows address of the
   contract and hash of the transaction the contract was deployed by)

## TODO ##

- Write tests
- Clean and add comments
