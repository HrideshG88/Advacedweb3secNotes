#Description: Understanding and implementing perpetuals protocol

# Perpetuals

Basically a type of protocol with which users can use high amounts of leverage to bet on a price of an index and make more profits than they otherwise would.

High risk : high reward

## Key Elements

- Liquidity Providers: the ones providing assets that are used to pay out traders(when they profit)
  - makes money when trader liquidates.
  - makes money with fees by providing assets
- Traders: the ones opening positions and betting on prices
  - Max leverage
  - Protocol Fee
  - Positions(long/short)
  - user P&L
- Open Interest: total amount loaned out by liquidity providers(virtually)
- Liquidity Reserves: there to manage risks for LPs and reward for traders.

## Position Scenarios

### Long Position

Betting on price of an asset to go up.

**ETH = $2000**

- Collateral = $500
- size(collateral \* leverage) = $5000 (10x Leverage)
- size in Tokens = 2.5 Eth (5000/2000)

#### Case 1: Price Increase

**ETH = $3000**

- Collateral = $500
- size = $5000
- size in Tokens = 2.5 ETH
- Value = $7500
- profit = $2500 (currentValue - borrowedAmount)
- Leverage = 5000/500 = 10x

> Depending on the protocol profit can be included or secluded from this calculation.If **profit is included** here it would enable a user to **have a position with 0 collateral**.

#### Case 2: Price Decrease

**ETH = $1750**

- Collateral = $500
- size = $5000
- size in Tokens = 2.5 ETH
- Value = $4375
- Profit = -$625
- Leverage = 5000/-125 = 40x = liquidation

### Short Position

Betting on price of asset to go down

**ETH = $2000**

- Collateral = $500
- size(collateral \* leverage) = $5000 (10x Leverage)
- size in Tokens = 2.5 Eth (5000/2000)

#### Case 1: Price Decrease

**ETH = $1750**

- Collateral = $500
- size = $5000
- size in Tokens = 2.5 ETH
- Value = $4375
- Profit = $625 (BorrowedAmount - CurrentValue)
- Leverage = 5000/500 10x

#### Case 2: Price Increase

**ETH = $3000**

- Collateral = $500
- size = $5000
- size in Tokens = 2.5 ETH
- Value = $7500
- profit = -$2500(BorrowedAmount - CurrentValue)
- Leverage = 5000/-2000 = -2.5x (Think I hit an edgecase with these numbers)
