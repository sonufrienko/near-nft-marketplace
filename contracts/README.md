# Contracts

- `fungible-token` - Fungible Token (FT)
- `non-fungible-token` - Non-fungible Token (NFT)

## Build

Build all contracts in Cargo Workspace

```sh
./build.sh
```

## Deploy

Deploy FT contract

```sh
export FT=ft.sergiio.testnet
near deploy --wasmFile res/fungible_token.wasm --accountId $FT
```

Deploy NFT contract

```sh
export NFT=nft.sergiio.testnet
near deploy --wasmFile res/non_fungible_token.wasm --accountId $NFT
```

## Manage NEAR accounts

Delete account

```sh
near delete nft.sergiio.testnet sergiio.testnet
```

Create sub account

```sh
near create-account nft.sergiio.testnet --masterAccount sergiio.testnet --initialBalance 30
```

Import sub account to NEAR Wallet

```sh
https://wallet.testnet.near.org/auto-import-secret-key#<YOUR_ACCOUNT_ID>/<YOUR_PRIVATE_KEY>
```

Send token from one account to another

```sh
near send <FROM> <TO> 10
```
