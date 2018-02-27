
# LETS on Ethereum


**Information about LETS**

* [LETS and mutual credit](http://www.letslinkuk.net/home/theory.htm)
* [Wikipedia LETS](https://en.wikipedia.org/wiki/Local_exchange_trading_system)


**Information about Ethereum**

* [Ethereum project](https://www.ethereum.org/)
* [How Ethereum will change the world (video)](https://reason.com/blog/2016/03/18/ethereum-lubin-freedom-consensys)

**Current LETS system online**

* [LETS Australia](https://communityexchange.net.au/)

**TODO : need to go through the process of doing a trade on this system, and make another document (with pictures) showing the process**



# LETS on Ethereum : The plan

There are 3 main components for this planned approach :

1. a PoA network to host it
2. an ERC20 smart contract that allows -ve balances
3. app that allows offline transactions 

*These notes are originally made on 27 Feb 2018, they represent the planned approach*

## 1. PoA network

We will create our own Ethereum chain.  
We will use the Proof of Authority consensus protocol, rather than the (current) Proof of Work protocol used by Ethereum main net.   
Proof of Authority has the following advantages for our purposes :   

* no mining, so removal of the excess energy consumption environmental concern
* finality (no risk of the chain history being rewritten)

It also implies/requires that only trusted nodes join the chain, which we consider to be fine for our LETS blockchain.

Here are my experiments with PoA, including reference links :    
[https://github.com/krisrandall/ethereum-chain-with-poa-consensus](https://github.com/krisrandall/ethereum-chain-with-poa-consensus)

## 2. ERC20 smart contract

This actually, we think, can be pretty simple; a standard ERC20 token that allows -ve balances.    

The current LETS system does hold user details, so we will investigate the link between Ethereum address and user account, and almost certainly that will be simply handled via uPort.    
Possibly the token contract itself will require 

The smart contract will also need to check for correct signatures by the buyer of transactions when those transactions come onto the chain (see below).



## 3. Offline mobile app

Independent of a blockchain backend it has been identified that a mobile app with great UX and UI is really needed as part of revitalising LETS in the 21st century.   
The app must be "sexy" !


We want this app to operate offline.  
The idea is that the buyer will initiate the "purchase" in their app, a QR code that contains the details of the transaction will be shown on their phone (signed by the buyer), the seller will "capture" the QR code on their phone - that then represents the transfer of the LETS currency to them, their app will be the one that sends the transaction to the chain when it is online.

So the app must have a local database of transactions, with a sync status field to keep track of the movement of the transactions to the chain.


#### Resources

* How to do an offline signing :    
  [https://programtheblockchain.com/posts/2018/02/17/signing-and-verifying-messages-in-ethereum/](https://programtheblockchain.com/posts/2018/02/17/signing-and-verifying-messages-in-ethereum/)
* My early experiements with signing :    
  [https://github.com/krisrandall/signing_overview](https://github.com/krisrandall/signing_overview)




