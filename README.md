# How to create and launch a token on Solana

## Task Overview
[] Install the Solana CLI

[] Set up a wallet to hold your SOL

[] Send SOL to your wallet

[] 

## Install tools

### Install Solana CLI

Follow instructions at https://docs.solanalabs.com/cli/install

or run command

```bash
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```

Restart terminal to update your PATH environment variable

### Install Rust

Update your apt registry

```bash
sudo apt update
```

Install Rust

```bash
curl https://sh.rustup.rs -sSf | sh

# select option 1 for the default install
```

Exit your terminal and relaunch to update your PATH

Install these dependencies

```bash
sudo apt install libudev-dev -y
sudo apt install libssl-dev pkg-config -y
sudo apt install build-essential -y
```

### Install the Solana Token Program CLI

```bash
cargo install spl-token-cli
```

## Create your token

### Create your Solana wallet

```bash
solana-keygen new
```

***BACKUP YOUR SEED PHRASE AS THIS IS VITAL FOR RECOVERING YOUR WALLET***

You can check your balance with this command

```bash
solana balance
```

You can get your wallet address by calling the below command

```bash
solana address
```

### Send SOL to your wallet
You will need SOL in your wallet to cover fees and for setting up your Liquidity Pool (LP), so transfer some SOL to your wallet using the public wallet address.

### Create your token

```bash
spl-token create-token
```

Create a Token Account

```bash
spl-token create-account yourTokenAddress
```

Mint some tokens!

```bash
spl-token mint yourtokenaddress amountyouwanttomint yourtokenaccount
```

e.g. Minting 1 Billion tokens

```bash
spl-token mint FHA21qfo6wFMfEA1isTQWSJ9RLcXT8gxJ5Mxv2vb 1000000000 wy2zKmPBWyXF0cvvqtMoLEEAbZ4v4vYdTtX3ckUAF
```

### Send some of your token to another wallet

```bash
spl-token transfer --fund-recipient --allow-unfunded-recipient yourTokenAddress amountToSend targetWalletAddress
```

--allow-unfunded allows the recipient to receive the tokens when they don't already have some

Example:

```bash
spl-token transfer --fund-recipient --allow-unfunded-recipient FHA21qfo6wFMfEA1isTQWSJ9RLcXT8gxJ5Mxv2vb 10000000 RECIPIENTADDRESS
```

Each of these transfers will cost SOL from your account

## Add Metadata to your token

The next step



## Useful Links

Network Chuck Video - NOTE THAT METADATA SOLUTION NO LONGER SUPPORTED - https://www.youtube.com/watch?v=befUVytFC80