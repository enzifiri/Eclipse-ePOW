bitz contract
```
64mggk2nXg6vHC1qCdsZdEFzd5QGN4id54Vbho4PswCF
```

### Preparing the server
```console
# First, update your distro
sudo apt update && apt upgrade -y

# Install dependencies
apt install build-essential git curl gcc make jq clang protobuf-compiler pkg-config libssl-dev -y

# Install Rust:
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# source config
source ~/.profile
source ~/.cargo/env

# Install Solana CLI:
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash

. "$HOME/.cargo/env"
export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"
```

### Creating wallet and RPC config

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

### Installing bitz. Cargo builds might take some time. Wait until end.
```console
# Installing bitz
cargo install bitz

# screen olustur
screen -S bitz

# Collect bitz:
bitz collect
bitz collect --cores 4

# Claim your bitz:
bitz claim

# Check your balance:
bitz account

# Look up all commands:
bitz -h or bitz --help
```

