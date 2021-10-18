# Blockchain-Python-Network-
For this project, I took on the role of a startup that is focusing on building a portfolio management system that supports not only traditional assets like gold, silver, stocks, etc, but crypto-assets as well! I have utilized a command line tool, hd-wallet-derive that supports not only BIP32, BIP39, and BIP44, but also supports non-standard derivation paths for the most popular wallets out there today. In addition, I have integrated the script into my backend using Python.For simplicity, I have only gotten the following 2 coins working: Ethereum and Bitcoin Testnet.

## Install Instruction

Create a project directory called wallet and cd into it.

Clone the hd-wallet-derive tool into this folder and install it using the HD Wallet Derive Installation Guide

Create a symlink called derive for the hd-wallet-derive/hd-wallet-derive.php script. This will clean up the command needed to run the script in our code, as we can call ./derive instead of ./hd-wallet-derive/hd-wallet-derive.php

In a separate file, constants.py, set the following constants:
BTC = 'btc'
ETH = 'eth'
BTCTEST = 'btc-test'

In wallet.py, import all constants: from constants import *

Generate a new 12 word mnemonic

Set this mnemonic as an environment variable by storing it a an .env file and importing it into your wallet.py

Create a function called derive_wallets that does the following:

Use the subprocess library to create a shell command that calls the ./derive script from Python. Make sure to properly wait for the process. Windows Users may need to prepend the php command in front of ./derive like so: php ./derive.

The following flags must be passed into the shell command as variables:

Mnemonic (--mnemonic) must be set from an environment variable, or default to a test mnemonic
Coin (--coin)
Numderive (--numderive) to set number of child keys generated
Format (--format=json) to parse the output into a JSON object using json.loads(output)

Create a dictionary object called coins that uses the derive_wallets function to derive ETH and BTCTEST wallets.
