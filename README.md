# Aurum.dc
Just a really fast and secure implementation of a blockchain for a cryptocurrency made in Python. The goal of this project is to make a working blockchain currency, keeping it as protect and fastest as possible.


## What is a blockchain?

Taking a look at the [Bitcoin organization wiki website](https://en.bitcoin.it/wiki/Main_Page) we can find this definition:

>A block chain is a transaction database shared by all nodes participating in a system based on the Bitcoin protocol. A full copy of a currency's block chain contains every transaction ever executed in the currency. With this information, one can find out how much value belonged to each address at any point in history. 

You can find more information in the original [Bitcoin Paper](https://bitcoin.org/bitcoin.pdf).

## How to run it

First, install ```requirements.txt```.

```
pip install -r requirements.txt
```

Then you have 2 options:

- Run ```miner.py``` to become a node and start mining
- Run ```wallet.py``` to become a user and send transactions (to send transactions you must run a node, in other words, you must run ```miner.py``` too)

> Important: DO NOT run it in the python IDLE, run it in your console. The ```miner.py``` uses parallel processing that doesn't work in the python IDLE.

## How this code work?

There are 2 main scripts:

- ```miner.py```
- ```wallet.py```

### Miner.py

This file is probably the most important. Running it will create a node (like a server). From here you can connect to the blockchain and process transactions (that other users send) by mining. As a reward for this work, you recieve some coins. The more nodes exist, the more secure the blockchain gets.

```miner.py``` has 2 processes running in parallel:

1. The first process takes care of mining, updating new blockchains and finding the proof of work.

2. The second process runs the flask server where peer nodes and users can connect to ask for the entire blockchain or sumbmit new transactions.

> Parallel processes don't run in python IDLE, so make sure you are running it from the console.

![miner](https://i.ibb.co/vwFrMYN/image-2020-12-05-212518.png)

### Wallet.py

This file is for those who don't want to be nodes but simple users. Running this file allows you to generate a new address, send coins and check your transaction history (keep in mind that if you are running this in a local server, you will need a "miner" to process your transaction).
When creating a wallet address, a new file will be generated with all your security credentials. You are supposed to keep it safe.

![wallet](https://i.ibb.co/PWsjcbG/image-2020-12-05-212648.png)


## Contribution

Anybody is welcome to collaborate in this project. Feel free to push any pull request (even if you are new to coding). See ```CONTRIBUTING.md``` to learn how to contribute.

Note: the idea of this project is to build a **really simple and secured** blockchain system.
