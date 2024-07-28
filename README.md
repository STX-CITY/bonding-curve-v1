
## How the Bonding Curve DEX Contract Works

The DEX starts with a certain amount of STX (the main cryptocurrency on the Stacks blockchain) and a certain number of tokens.

When someone wants to buy tokens, they send STX to the DEX. The DEX then gives them a certain number of tokens based on a formula in the code.

As more people buy tokens, the price of the tokens goes up, following a "bonding curve." This means that the more tokens that are bought, the more expensive each additional token becomes.

When someone wants to sell their tokens, they send the tokens back to the DEX, and the DEX gives them STX in return, based on the same formula.

Once the DEX has reached a certain amount of STX (the "STX_TARGET_AMOUNT"), the DEX will automatically "complete" the bonding curve. This means that the DEX will burn (or destroy) any remaining tokens and send the remaining STX to a special address called the "VELAR_ADDRESS."

The bonding curve DEX uses the simple formula like a normal AMM DEX:
k = x * y

## What Happens if the Bonding Curve is Completed?

There is the concept called the Last Buyer who triggers tradable to be disabled on the bonding curve DEX.

The target is 10k STX, and the current balance of the DEX is 9900. If you buy above 100 STX, you will be the last buyer.

If you are the last buyer, after you receive tokens, here is how it works:

1. The DEX will burn 20% of the remaining tokens, creating an inflationary boost for the token.
2. The DEX will send the STX and token amount to a Velar DEX. The Velar team will pair STX with the token to create a trading pair and add liquidity for the token.
3. Trading on the bonding curve is completed, and users can no longer swap on the bonding curve.

## Summary

- Each token will be paired with one bonding curve DEX.
- After the user deploys a bonding curve token, they have to deploy a bonding curve DEX.
- In the token's contract, the total supply will be sent to the DEX's balance.
- The DEX starts with 0 STX and 10B tokens.
- The DEX ends at {target} STX.
- After transfer to Velar, the DEX balance should be 0 STX and 0 tokens.

## Audited & Secured Bonding Curve Contract

STXCITY's bonding curve contract has undergone a comprehensive security audit by the Gecko Security [(@gecko_sec)](https://x.com/gecko_sec). Their rigorous review process ensures our contract meets the highest standards of security and reliability.

In addition to the audit, we have successfully conducted two rounds of testing on our testnet [round 2](https://x.com/stxcity/status/1815416071966585148) [round 1](https://x.com/stxcity/status/1811675675881034059), with hundreds of participants actively engaging with the platform. This real-world testing has further strengthened the security and stability of our bonding curve contract.

At STXCITY, we prioritize providing a secure and trustworthy platform for our community. The audit by Gecko Security and successful testnet rounds demonstrate our commitment to delivering a robust and reliable solution for decentralized finance on the Stacks blockchain.

Audit file: [gecko_stxcity_audit_final.pdf](https://drive.google.com/file/d/13UlAxNzfJ0fwH3g1ddaqOJJed4RzRn5d/view?usp=sharing)

## Test steps:

::set_tx_sender ST3PF13W7Z0RRM42A8VZRVFQ75SV1K26RXEP8YGKJ

### Buy tokens

(contract-call? 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.bonding-curve-dex buy 'ST1PQHQKV0RJXZFY1DGX8MNSNYVE3VGZJSRTPGZGM.welsh u100000000)


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
