# Unified Trading Account

The unified account is a next-generation trading system introduced by Bitget, designed to allow users to trade spot and various derivatives using multiple crypto assets within a single account. This system simplifies the trading process by eliminating the need for fund transfers between different accounts. Moreover, profits and losses across different products can be calculated and offset together, enhancing capital efficiency.

## Comparison of Account Modes[​](#comparison-of-account-modes "Direct link to Comparison of Account Modes")

The unified account offers three new account modes to meet diverse trading preferences and needs: **single-asset margin** (coming soon), **multi-assets margin**, and **portfolio margin** (coming soon). Details are as follows,

| Account Mode | Features | Eligibility |
| --- | --- | --- |
| Single-asset margin (coming soon) | Supported trading types  *Spot trading*  *Margin trading*  *USDT perpetual futures*  *USDC perpetual futures*   *Coin-M perpetual futures*  *Coin-M delivery futures*    In single-asset cross margin mode, all trading types with the same settlement currency share the margin, and profits and losses across different products can be calculated and offset together. | All registered users. This is the default account mode. |
| Multi-assets margin (available now) | Supported trading types  *Spot trading*  *Margin trading*  *USDT perpetual futures*  *USDC perpetual futures*   *Coin-M perpetual futures*(coming soon)   In multi-assets cross margin mode, all trading types share the margin, and profits and losses across different products can be calculated and offset together. | Trading account equity needs to be at least $10,000 and users must complete the quiz to activate the mode. |
| Portfolio margin (coming soon) | Supported trading types  *Spot trading*  *Margin trading*  *USDT perpetual futures*  *USDC perpetual futures*   *Coin-M perpetual futures*  *Coin-M delivery futures*   In portfolio margin mode, all trading types share the margin, and margins for all derivatives with the same index can be calculated together. Profits and losses across different products can also be calculated and offset. | Trading account equity needs to be at least $10,000 and users must complete the quiz to activate the mode. |

## Asset-related Terminology[​](#asset-related-terminology "Direct link to Asset-related Terminology")

| Term | Explanation |
| --- | --- |
| Equity | The total equity of a specific coin in the cross margin account. *Coin equity = Balance + Frozen margin + unrealized PnL* |
| Balance | The balance of a specific coin in the account. |
| Available | The current available balance of a specific coin in the account for opening positions. *Available = Balance + unrealized PnL* Note: Realized PnL in the available balance can be used for opening futures positions but cannot be used to place spot orders. |
| UnrealisedPnL | The total profits of all futures positions settled in a specific coin in the account.  *Unrealized profits = Profits of USDT-M perpetual futures positions in cross margin mode + profits of USDC-M perpetual futures positions in cross margin mode + profits of coin-M perpetual futures positions in cross margin mode* |
| Debt | Debt = ABS(min(balance + unrealized PnL, 0)) |
| Account equity | The net value of all coin assets in the account converted into fiat currency. *Account equity = sum (coin equity × coin in USD price)* |
| Maintenance margin | The total maintenance margin of all cross margin positions in the account.  *Maintenance margin = Sum[quantity of coin in cross margin positions × coin price]* *Maintenance margin = Position value × maintenance margin rate* |
| Margin rate | A risk measurement indicator for cross margin accounts.  *Cross margin account's margin ratio = (maintenance margin + partial liquidation transaction fees)÷Account equity*. Both maintenance margin and partial liquidation transaction fees are calculated by adding the position size and the open order size. |

## Improved Readability[​](#improved-readability "Direct link to Improved Readability")

The Open API documentation has been revised and proofread, with unclear descriptions from previous versions clarified to reduce customer confusion.