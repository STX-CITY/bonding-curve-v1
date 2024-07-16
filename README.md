## Test steps:

:set_tx_sender ST3PF13W7Z0RRM42A8VZRVFQ75SV1K26RXEP8YGKJ

### Buy tokens

(contract-call? 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.bonding-curve-dex buy 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.welsh u100000000)(contract-call? 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.bonding-curve-dex sell 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.welsh u1000000000)

### Sell tokens
(contract-call? 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.bonding-curve-dex sell 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.welsh u668440171228715)

### Helpers
(contract-call? 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.bonding-curve-dex get-buyable-tokens u1000000 )

(contract-call? 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.bonding-curve-dex get-sellable-stx  u1000000000 )

::get_assets_maps

## Deployment Summary

Step 1: Creation of the Token
You will create a token named 'XYZ' with a total supply of 10 billion.

Step 2: Sending to DEX
Then the contract will send all 10 billion XYZ to a bonding curve DEX. Users can immediately buy or sell XYZ on that bonding curve DEX.

Step 3: Initial Pricing
The initial price of XYZ is: $0.0000033

Step 4: Market Cap Goal
When the market cap reaches 10,000 STX, all the liquidity ($STX and XYZ) from the bonding curve DEX will be deposited into a Velar address.

Step 5: Trading Pair and Liquidity
After that, the Velar team will create a trading pair and add liquidity for XYZ.
Estimated market cap by then: $16,691.316