---
title: Parity Ethereum CLI Sub-commands
---

## Export blockchain state

Example: `parity export state ./export-state-file.bin`

This command allows exporting the state of a given blockchain (specified with `--chain`) to a file.
This command requires the chain to be synced with --fat-db on.

### Flags:
- `--no-code`       Don't export account code.
- `--no-storage`    Don't export account storage.

### Options:
- `--at <BLOCK>`           Take a snapshot at the given block, which may be an index, hash, or latest. Note that taking snapshots at non-recent blocks will only work with --pruning archive
- `--format <FORMAT>`      Export in a given format. FORMAT must be either 'hex' or 'binary'. (default: binary)
- `--max-balance <WEI>`    Don't export accounts with a balance greater than specified.
- `--min-balance <WEI>`    Don't export accounts with balance less than specified.

## Export blockchain blocks

Example: `parity export blocks ./export-blocks-file.bin`

This command allows exporting the block of a given blockchain (specified with `--chain`) to a file.
This command requires the chain to be synced with --fat-db on.

### Options:
- `--format <FORMAT>`    Export in a given format. FORMAT must be either 'hex' or 'binary'. (default: binary)
- `--from <BLOCK>`       Export from block BLOCK, which may be an index or hash.
- `--to <BLOCK>`         Export to (including) block BLOCK, which may be an index, hash or latest.

## Import blockchain from file

Example: `parity import ./export-blocks-file.bin`

This command allows exporting the block of a given blockchain (specified with `--chain`) to a file.

### Options:
- `--format <FORMAT>`    Import in a given format. FORMAT must be either 'hex' or 'binary'. (default: auto)

## Create accounts

This command creates a new account (and its associated key) for the specified blockchain (default mainnet).

Example :
```bash
parity --chain kovan account new
Loading config file from users.toml
Please note that password is NOT RECOVERABLE.
Type password: 
Repeat password:
0x66a4b6f39b4c3e7203ab9caeecbad58d8f29b046
```


## List accounts

This command list existing accounts for the specified blockchain (default mainnet).

Example:
```bash
parity --chain kovan account list
0x00780865dcc3c7dbffd943136107e70b8270286b
0x00dfc93112abd2578503b667b95491b101281f2b
```

## Import accounts

This command lets you import accounts from JSON UTC keystore files to the specified blockchain (default mainnet).

Example
```bash
parity --chain kovan account list
0x00780865dcc3c7dbffd943136107e70b8270286b
0x00dfc93112abd2578503b667b95491b101281f2b


$ parity account import --chain kovan ./keystore-file.json 
1 account(s) imported

$ parity --chain kovan account list
0x003324332f7a9c2fb9536fcc4246a0bb4ea1b63f
0x00780865dcc3c7dbffd943136107e70b8270286b
0x00dfc93112abd2578503b667b95491b101281f2b
```

## Parity Daemon

Launch Parity Ethereum as a daemon.

Example:
`parity daemon ~/parity-daemon.pid --chain kovan`



## Signer new token generation

This command generates a token for Parity Ethereum UI to be able to connect to the node.

Example:
```bash
parity signer new-token

Or use the generated token:
xAtk-66Q1-lPu5-b2o8
```


