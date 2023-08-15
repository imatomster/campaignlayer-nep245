# CampaignLayerNEP245 Smart Contract

The CampaignLayerNEP245 smart contract is designed to provide multi-token management functionality on the NEAR Protocol. It adheres to the NEAR Contract Standards for Multi-Token and includes features for token minting, transferring, approvals, batch transfers, and now token burning.

## Functions

### `new_default_meta(owner_id: AccountId)`

Initializes the contract with default metadata.

### `new(owner_id: AccountId, metadata: MtContractMetadata)`

Initializes the contract with custom metadata.

### `mt_mint(token_owner_id: AccountId, token_metadata: TokenMetadata, supply: Balance) -> Token`

Mints new tokens and assigns them to a specified account.

### `register(token_id: TokenId, account_id: AccountId)`

Registers an account as the owner of a specific token.

### `mt_transfer(receiver_id: AccountId, token_id: TokenId, amount: U128, memo: Option<String>, msg: Option<String>)`

Transfers tokens from the caller's account to another account.

### `mt_batch_transfer(receiver_id: AccountId, token_ids: Vec<TokenId>, amounts: Vec<U128>, memos: Option<Vec<String>>, msgs: Option<Vec<String>>)`

Transfers batches of tokens from the caller's account to another account.

### `mt_approve(token_ids: Vec<TokenId>, amounts: Vec<U128>, account_id: AccountId, msg: Option<String>)`

Approves an account to spend a specific amount of tokens on behalf of the caller.

### `mt_revoke(token_ids: Vec<TokenId>, account_id: AccountId)`

Revokes approval for an account to spend tokens.

### `mt_revoke_all(token_ids: Vec<TokenId>)`

Revokes all approvals for a set of token IDs.

### `mt_balance_of(account_id: AccountId, token_id: TokenId) -> U128`

Retrieves the balance of a specific token for a given account.

### `mt_is_approved(token_ids: Vec<TokenId>, account_id: AccountId, amounts: Vec<U128>, msg: Option<String>) -> bool`

Checks if an account is approved to spend a specific amount of tokens.

### `mt_burn(token_id: TokenId, amount: U128)`

Burns a specified amount of tokens owned by the caller, reducing the token supply.

## Deploying the Smart Contract

1. Clone this repository to your local machine.
2. Install the necessary tools: Rust, Rustup, and NEAR CLI.
3. Compile the smart contract: Run `cargo build --target wasm32-unknown-unknown --release` in the project root directory.
4. Deploy the smart contract: Use NEAR CLI to deploy the compiled Wasm file to the NEAR Protocol.

Example deployment command:

```sh
near deploy --wasmFile target/wasm32-unknown-unknown/release/campaignlayernep245.wasm --accountId YOUR_ACCOUNT_ID
```
