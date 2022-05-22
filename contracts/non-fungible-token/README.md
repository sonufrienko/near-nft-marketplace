# Non-fungible Token (NFT)

## API

- Init contract

  ```sh
  near call $CONTRACT new_default_meta '{"owner_id": "'$CONTRACT'"}' --accountId $CONTRACT
  ```

- View metadata

  ```sh
  near view $CONTRACT nft_metadata
  ```

- Mint

  ```sh
  near call $CONTRACT nft_mint '{"token_id": "token-1", "metadata": {"title": "Demo NFT", "description": "Some text", "media": "https://images.unsplash.com/photo-1589180176337-503fed4bcfe0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8"}, "receiver_id": "'$CONTRACT'"}' --accountId $CONTRACT --amount 0.1
  ```

## Check state

```sh
near state $CONTRACT
near view-state $CONTRACT --finality final
```

## Delete contract

```sh
near delete $CONTRACT sergiio.testnet
near create-account nft.sergiio.testnet --masterAccount sergiio.testnet --initialBalance 30
```

## Import sub account to NEAR Wallet

Open in browser

```
https://wallet.testnet.near.org/auto-import-secret-key#<YOUR_ACCOUNT_ID>/<YOUR_PRIVATE_KEY>
```
