# Eclipse ePOW

### Eclipse announced its new technology epow (RIP eCOW) and said that it will be able to work in many places including mobile devices in the future. 
As someone who likes to try new things, I install it without any financial expectation and I explain it to you in a simple way (the installation steps are already explained quite simply)

I installed using Ubuntu 24 on my 8CPU 16GB RAM Intel device. 

In short, you earn $BITZ tokens by mining. There is no financial return for the moment.


Preparing the server
```console
# First, update your distro
sudo apt update && apt upgrade -y

# Install dependencies
apt install build-essential git curl gcc make jq clang protobuf-compiler pkg-config libssl-dev -y

# Install Rust:
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install Solana CLI:
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

Creating wallet and RPC config

After wallet creation, backup your seeds and id.json.

Copy the output `cat ~/.config/solana/id.json` with [] and import your eclipse wallet as private key. And fund at least 0.0005 ETH

```console
# Create wallet
solana-keygen new

# To see id.json. Copy the output with [] and import your eclipse wallet as private key. And fund at least 0.0005 ETH
cat ~/.config/solana/id.json

# RPC config
solana config set --url https://bitz-000.eclipserpc.xyz/

```

Installing bitz. Cargo builds might take some time. Wait until end.
```console
# Installing bitz
cargo install bitz

# Collect bitz:
bitz collect

# Claim your bitz:
bitz claim

# Check your balance:
bitz account

# Look up all commands:
bitz -h or bitz --help
```

