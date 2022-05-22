# Fungible Token (FT)

[Fungible Token Standard](https://nomicon.io/Standards/Tokens/FungibleToken/)

## API

- Init contract

  `symbol` = WATT

  `total_supply` = 10M coins

  `decimals` = 8

  ```sh
  export FT=ft.sergiio.testnet
  near call $FT new '{"owner_id": "'$FT'", "total_supply": "1000000000000000", "metadata": { "spec": "ft-1.0.0", "name": "Energy Game Token", "symbol": "WATT", "decimals": 8 }}' --accountId $FT
  ```

- Retrieve metadata

  ```sh
  near view $FT ft_metadata
  ```

- Get Total Token Supply

  ```sh
  near view $FT ft_total_supply
  ```

- Get Token Balance of Owner

  ```sh
  near view $FT ft_balance_of '{"account_id": "sergiio.testnet"}'
  near view $FT ft_balance_of '{"account_id": "'$FT'"}'
  ```

- Transfer Tokens to Another Account

  Transfer 1.5 WATT to "sergiio.testnet"

  ```sh
  near call $FT ft_transfer '{"receiver_id": "sergiio.testnet", "amount": "150000000"}' --accountId $FT --amount 0.000000000000000000000001
  ```

- Transfer Tokens from one user to another

  ```sh
  near call $FT ft_resolve_transfer '{"sender_id": "", "receiver_id": "", "amount": ""}'
  ```

## Storage Management

- Paying for account registration, aka storage deposit

  ```sh
  near call $FT storage_deposit '' --accountId sergiio.testnet --amount 0.6888
  ```

- Retrieve storage balance

  ```sh
  near view $FT storage_balance_of '{"account_id": "sergiio.testnet"}'
  near view $FT storage_balance_bounds
  ```
