# Setting up a Miner Node

[![Testnet Phase Argon Badge](https://img.shields.io/static/v1?label=Stacks%202.0%20Testnet%20Phase&message=%232%20Argon&color=9cf&style=for-the-badge)](https://forum.blockstack.org/t/stacks-2-0-testnet-coming-soon/10510)

This repository contains a handy script that will help you run a Miner Node on the [Blockstack Stacks 2.0 Testnet](https://testnet.blockstack.org/)!

## Requirements

This script is designed for and tested on [Ubuntu Server 20.04 LTS](https://ubuntu.com/server).

In theory, it should work for any Ubuntu-based installation but [YMMV](https://dictionary.cambridge.org/us/dictionary/english/ymmv).

Before running the script, I recommend setting up a virtual machine using [Virtualbox](https://www.virtualbox.org/).

A step by step walkthrough of installing Virtualbox and setting up the Ubuntu Server virtual machine can be found at the link below as part of the [Zero to Testnet Blog Series](https://app.sigle.io/whoabuddy.id.blockstack/):

- [Step 0: Virtualbox + Ubuntu (Zero to Testnet Series)](https://app.sigle.io/whoabuddy.id.blockstack/6ZSqK6yEwu5bqqGCjOZZH)

The specifications I used for my Ubuntu Server virtual machine are listed and pictured below:

- Base Memory: 1024 MB (1gb RAM)
- Video Memory: 16 MB
- Hard Drive: 100 GB
- Network: Bridged Adapter

![Screenshot from 2020-06-02 09-21-11](https://user-images.githubusercontent.com/9038904/83544659-1b291580-a4b3-11ea-8ec9-ffb2cf16d52c.png)

## Using the Script

To run the script, simply use the command below! It will download the file from this repository and run it using `bash`.

```
curl -o- https://raw.githubusercontent.com/AbsorbingChaos/bks-setup-miner/master/config-miner-argon.sh | bash
```

To see a video of the script in action, check out [this YouTube link!](https://youtu.be/rOs8ZqCt_xM)

The script can be run multiple times, and will check for and complete the following tasks:

1. Install or update operating system prerequisites `build-essential cmake libssl-dev pkg-config jq git`
2. Detect or install node version manager (nvm)
3. Detect or install Node.js (via nvm)
4. Detect or install Rust (via rustup.rs)
5. Download or update the stacks-blockchain repository (via git)
6. Detect or create the keychain file (via blockstack-cli make_keychain)
7. Detect or request tBTC balance (via keychain file and [faucet](https://testnet.blockstack.org/faucet))
8. Detect or download miner configuration file (via GitHub)
    - If the miner configuration file is downloaded, automatically inserts the private key (via keychain file)
9. Check tBTC balance before starting the miner process
10. Start the miner and try to win the sortitions!

This link will allow you to [manually view or download the script](https://github.com/AbsorbingChaos/bks-setup-miner/blob/master/config-miner-argon.sh), if you are into that kind of thing.

## Final Word

Please note that this script is released under the [MIT License](LICENSE). __Please only run this script on a virtual machine setup for the purpose of mining on the Blockstack Stacks 2.0 Testnet, and please do not run this script on any system used in production.__

__*THIS IS FOR TESTING PURPOSES ONLY!*__

If you run into any issues with the script or have any general questions about the process, feel free to [file an issue here](https://github.com/AbsorbingChaos/bks-setup-miner/issues), or reach out to me via the [Blockstack Discord channel](https://community.blockstack.org/discord) @whoabuddy.
