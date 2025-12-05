# WebSocket Error Code

| Error Code | Description |
| --- | --- |
| 429 | Too Many Requests |
| 12001 | {0} can be used at most |
| 12002 | Current currency {0}, limit net sell value {1} USD |
| 12003 | Current currency {0}, limit net buy value {1} USD |
| 13007 | The current currency is {0}, and the net purchase value of {1} USD is limited within 24 hours, and the net purchase value of {2} USD is also allowed for {3} |
| 13008 | Traders minimum place orderSize is {0} |
| 13009 | Current currency {0}, 24-hour limit on net selling value {1} USD, you can also net sell {3} worth {2} USD |
| 22001 | No order to cancel |
| 22002 | No position to close |
| 22003 | modify price and size, please pass in newClientOid |
| 22004 | This symbol {0} not support API trade |
| 22005 | This symbol does not support cross mode |
| 22006 | limit price > risk price |
| 22007 | limit price < risk price |
| 22008 | market price > risk price |
| 22009 | market price < risk price |
| 22010 | Please bind ip whitelist address |
| 22011 | It is not allowed to set auto add margin in cross mode |
| 22013 | Abnormal status of position experience coupon |
| 22014 | This position experience coupon does not exist |
| 22015 | This user has no position experience coupon sub-account |
| 22016 | This user is not a sub-account for position experience coupons and cannot operate experience coupons |
| 22017 | The position experience coupon does not support this tokenId |
| 22018 | The face value of the position experience coupon is a negative number |
| 22019 | The position experience coupon has not expired yet |
| 22020 | The leverage multiple is the leverage multiple of the current position and cannot be adjusted. |
| 22021 | Limit orders are not supported when placing orders with position experience coupons |
| 22022 | The position experience coupon has been used |
| 22023 | The trial coupon for this position has expired |
| 22024 | The experience coupon for this position has been recycled |
| 22025 | Margin cannot be added to the experience coupon account |
| 22026 | The position mode cannot be adjusted for the experience coupon account |
| 22027 | The position experience coupon does not support this currency pair |
| 22028 | The position experience coupon does not support this type of order |
| 22029 | Risk control, you can currently open a maximum position of {0} {1}. The risk control proportion limit for a uid is calculated including all main accounts and sub-accounts |
| 22030 | UID:{0} Demo trading mode，can not use:{1} |
| 22033 | Trigger the risk control of position closing , prohibiting position closing |
| 22034 | Less than the minimum order amount |
| 22035 | Demo account open position too frequently |
| 22036 | API limits opening positions |
| 22037 | API limits closing positions |
| 22038 | Please enter the quantity as an integral multiple of {0} |
| 22039 | Limit open position when delivery is approaching. |
| 22040 | Limit open order when delivery is approaching. |
| 22041 | Limit close order when delivery is approaching. |
| 22042 | When a one-way position is held, trigger order cannot only reduce positions. |
| 22043 | ADL processing，{0} is limit close position |
| 22044 | ADL processing，cannot flash close Position |
| 22045 | Insufficient liquidity in the market, please operate later |
| 22046 | The order price exceeds the minimum price limit: {0} |
| 22047 | The order price exceeds the maximum price limit: {0} |
| 22048 | Exceeded personal limit, unable to delegate |
| 22049 | Exceeding the platform limit, unable to delegate |
| 22051 | For the current symbol, isolated position transfer to cross position will increase the risk of liquidation/reduction of positions, and the conversion cannot be completed. Please reduce the risk of holding positions |
| 22052 | {0} Currently there is an ongoing {1} airdrop position. Please close the position before opening another one. |
| 22053 | {0} Currently there is an ongoing {1} airdrop position. Please close the position before adjusting. |
| 22054 | there is a position or order for the current currency pair, the long and short leverages must be consistent when switching from isolated |
| 22055 | There are short positions or orders, and it is impossible to convert the isolated to crossed |
| 22056 | The symbol is not open for trade |
| 22057 | Market makers must be in one-way position holding mode and cannot place orders that only reduce positions |
| 22067 | ADL processing，forbid operate the symbol:{0} |
| 22069 | The current symbol does not support the cross-margin mode. Please switch to the isolated-margin mode. |
| 22070 | The current symbol only support the isolated-margin mode. |
| 22071 | Multi-assets mode only supports the cross-margin mode. Please switch the position mode for this symbol first. |
| 22072 | There are open isolated margin positions or orders. Please close the positions or cancel the orders before trying again. |
| 25001 | Operation timed out |
| 25002 | Unsupported operation |
| 25003 | Concurrent operation, please retry |
| 25004 | Operation too frequent, please try again later |
| 25005 | User does not exist |
| 25006 | Abnormal account status |
| 25007 | Account in an irregular status |
| 25008 | Account is in forced liquidation status |
| 25009 | Unsupported account mode switch |
| 25010 | Unsupported position mode switch |
| 25011 | Transfer failed, account is in forced liquidation status |
| 25012 | Account at risk, trading temporarily disabled |
| 25013 | {0} not support API trade |
| 25100 | Trading pair {0} does not exist |
| 25101 | Trading pair not open for trading |
| 25102 | Trading pair temporarily closed for maintenance |
| 25103 | Trading pair opening soon |
| 25104 | Contract delisted |
| 25105 | This contract does not support opening positions |
| 25106 | Trading suspended due to settlement or maintenance |
| 25107 | There is currently a position, please close the position |
| 25108 | The contract is in the initialization state |
| 25111 | The order price cannot be lower than the trigger price by {0}% |
| 25112 | The current Token has not enabled collateral. |
| 25201 | Currency does not exist |
| 25202 | Insufficient balance |
| 25203 | Insufficient margin |
| 25204 | Order does not exist |
| 25205 | {0} trading price cannot be below {1}% |
| 25206 | {0} trading price cannot exceed {1}% |
| 25207 | {0} trading quantity cannot be less than {1} units |
| 25208 | {0} trading quantity cannot exceed {1} units |
| 25209 | Insufficient market liquidity, please try again later |
| 25210 | Large price fluctuation, placing the order entails higher risk, please reorder |
| 25211 | Exceeds the limit of {0} maximum orders |
| 25212 | Duplicate clientOid |
| 25213 | Exceeds {0} permanent net buy limit, you can currently buy up to {1} USD worth of {0} |
| 25214 | Exceeds {0} permanent net sell limit, you can currently sell up to {1} USD worth of {0} |
| 25215 | Exceeds {0} 24-hour net buy limit, you can currently buy up to {1} USD worth of {0} |
| 25216 | Exceeds {0} 24-hour net sell limit, you can currently sell up to {1} USD worth of {0} |
| 25217 | Exceeds maximum repayment limit |
| 25218 | High risk, usage may result in forced liquidation |
| 25219 | Increase in IMR exceeds available assets |
| 25220 | RaiseImrTakeUp more than settleAvailable |
| 25221 | Level gradient does not exist |
| 25222 | Trade or fair mark price does not exist |
| 25223 | Exceeds Max. leverage |
| 25224 | Take-profit or stop-loss triggered warning, please proceed with cancellation |
| 25225 | Insufficient available quantity in position |
| 25226 | Insufficient total position quantity |
| 25227 | No position available to close |
| 25228 | Unable to update leverage for this position, insufficient margin! |
| 25229 | Total positions exceed the current limit of {0} positions |
| 25230 | Order quantity exceeds the maximum open quantity |
| 25231 | Close quantity cannot exceed the held position quantity |
| 25232 | Reduce-only orders will only reduce your position; please cancel or modify existing orders before placing a new one |
| 25233 | Order quantity cannot exceed the maximum for this level |
| 25234 | Remaining quantity for regular orders is {0} {1}, and for post-only orders it is {2} {3}. |
| 25235 | Due to risk control, the maximum open position currently allowed is {0} {1}. The risk control limit for a single user includes all primary and sub-accounts |
| 25236 | Incorrect position open type |
| 25237 | Close orders can only occur in bi-directional mode |
| 25238 | {0} do not assign values at the same |
| 25239 | Closing failed, please try again later |
| 25240 | {0} does not support this operation |
| 25241 | Bulk orders cannot exceed the corresponding maximum order value. |
| 25242 | The maximum reducible amount is {0}{1}. |
| 25243 | You have exceeded the currency holding limit and cannot add more of this currency. |
| 25244 | Price should be a multiple of {0} |
| 25245 | The account is not the unified account mode |
| 25270 | There are pending orders for contract bidirectional closing or contract unidirectional opening/reducing positions. |
| 25271 | The modification price and qty is the same as the original value. Please adjust and try again. |
| 25272 | Too many pending modification requests. Please try again later |
| 25273 | Skipped due to prior modification failure |
| 25274 | Reduce-only order protection |
| 25559 | Not loan user |
| 25560 | Subaccount the same with RiskUnit ID |
| 25561 | SubUid not in risk unit |
| 25562 | The subacccount is the other's Risk Unit |
| 25563 | The UID you are unbinding has a non-zero balance and has unsettled or pending loan orders in its associated risk unit. |
| 25564 | The number of sub-accounts under the risk unit has exceeded the limit. |
| 25565 | The sub-account UID you entered is already bound to another risk unit. |
| 25566 | The risk unit does not exist. |
| 25567 | Exceeded the maximum quantity of contract orders：{0} {1} |
| 25568 | The order does not meet the modification requirements. |
| 25569 | Exceeded the maximum limit for modifications. |
| 25575 | Exceeded the maximum quantity of contract orders: {0} {1} |
| 25654 | {0} trading price cannot be greater than the bankruptcy price of {1} {2}. |
| 25655 | {0} trading price cannot be lower than the bankruptcy price of {1} {2}. |
| 40000 | Bitget is providing services to many countries and regions around the world and strictly adheres to the rules and regulatory requirements of each country and region. According to the relevant regulations, Bitget is currently unable to provide services to your region and you do not have access to open positions.Apologies for any inconvenience caused! |
| 40015 | System is abnormal, please try again later |
| 40022 | The business of this account has been restricted |
| 40023 | The business of this account has been restricted |
| 40024 | he currency is a regional currency and does not meet the purchase conditions. |
| 40025 | The business of this account has been restricted |
| 40026 | User is disabled |
| 40027 | Withdrawals in this account area must be kyc |
| 40031 | The account has been cancelled and cannot be used again |
| 40035 | Judging from your login information, you are required to complete KYC first for compliance reasons. |
| 40042 | The account is an ins loan sub-account and is subject to business restrictions. For more details, please contact customer service. |
| 40103 | based on your IP address , it appears that you are located in a country or region where we are currently unable to provide services |
| 40104 | Unable to withdraw to this account Please make sure this is a valid and verified account |
| 40105 | Currently Spot Demo trade does not support this feature |
| 40115 | The unified account is undergoing an upgrade (rollback in progress). This operation is temporarily unavailable. Please try again later. |
| 40128 | The current feature is not supported under Unified Account mode. |
| 40710 | Abnormal account status |
| 40715 | delegate count can not high max of open count |
| 40760 | Unable to place order due to ongoing liquidation |
| 40761 | The total number of unfilled orders is too high |
| 40763 | Exceeds position tier limit |
| 40769 | Reject order has been completed |
| 40774 | The order type for unilateral position must also be the unilateral position type |
| 40775 | The market-making account can only be a unilateral position type. |
| 40779 | Please check that the correct delegateType is used |
| 40780 | There are multiple risk handling records for the same symbolId at the same time |
| 40781 | The transfer order was not found |
| 40782 | Internal transfer error |
| 40783 | No gear found |
| 40784 | Need to configure modify depth account |
| 40785 | Need to configure draw line account |
| 40788 | Internal batch transfer error |
| 40789 | The tokenId is duplicated in the configuration item |
| 40790 | Duplicate symbolCode in configuration item |
| 40791 | The baseToken or quoteToken of symbolCode does not exist |
| 40792 | The symbol in the configuration item is duplicated |
| 40793 | The symbolCode of BusinessSymbol does not exist |
| 40794 | The supportMarginToken of BusinessSymbol is not configured |
| 40798 | Insufficient contract account balance |
| 40799 | Cannot be less than the minimum transfer amount |
| 40800 | Insufficient amount of margin |
| 40801 | Cannot exceed the maximum transferable deposit amount |
| 40802 | Position is zero and direct margin call is not allowed |
| 40804 | The number of closed positions cannot exceed the number of positions held |
| 40805 | Unsupported operation |
| 40806 | Unsupported currency |
| 40807 | The account does not exist |
| 40808 | Parameter verification exception {0} |
| 40811 | The parameter {0} should not be null |
| 40812 | The condition {0} is not met |
| 40813 | The parameter {0} must have a value and cannot be empty |
| 40815 | The order price is higher than the highest bid price |
| 40816 | The order price is lower than the lowest selling price |
| 40820 | The order price for closing a long position is not allowed to be lower than the liquidation price |
| 40821 | The closing order price cannot be higher than the liquidation price |
| 40822 | The contract configuration does not exist |
| 40823 | The transaction or reasonable marked price does not exist |
| 40824 | Currently, it is not allowed to list market orders |
| 40825 | Contract opponent depth does not exist |
| 40826 | Due to excessive price fluctuations, the market order cost is insufficient, and the position opening order failed. |
| 40827 | The bonus is not allowed to hold two-way positions |
| 40828 | Special market making accounts cannot manually place orders |
| 40829 | The take profit price of a long position should be greater than the average open price |
| 40830 | The take profit price of the long position should be greater than the current price |
| 40831 | The short position take profit price should be less than the average open price |
| 40832 | The take profit price of short positions should be less than the current price |
| 40833 | The stop loss price of a long position should be less than the average opening price |
| 40834 | The stop loss price of the long position should be less than the current price |
| 40835 | The stop loss price of the short position should be greater than the average opening price |
| 40836 | The stop loss price of the short position should be greater than the current price |
| 40838 | There is no position in this position, and automatic margin call cannot be set |
| 40839 | The automatic margin call function of this contract has been suspended |
| 40840 | Duplicate shard market making account |
| 40841 | Online environment does not allow execution |
| 40842 | Current configuration does not allow adjustment, please try again later |
| 40843 | no\_datasource\_key\_exists |
| 40844 | This contract is under temporary maintenance |
| 40845 | This contract has been removed |
| 40846 | Status verification abnormal |
| 40847 | The operation cannot be performed |
| 40848 | Cannot open a copy transaction if there is a position |
| 40850 | The copy is in progress, the balance cannot be transferred |
| 40851 | Account status is wrong, cannot end copying |
| 40852 | There are unfilled orders, cannot end the copy |
| 40853 | There is an unexecuted plan order, cannot end the copy |
| 40854 | This product does not support copy trading |
| 40855 | The user has ended copying and cannot end copying again |
| 40856 | Data abnormal |
| 40858 | Error tracking order status |
| 40859 | This order is being closed and cannot be closed again |
| 40860 | The trader does not exist and cannot be set to follow |
| 40861 | The trader has been disabled and cannot be set to follow |
| 40862 | Please cancel the current order |
| 40863 | Please cancel the current plan |
| 40864 | Please close the current position with orders |
| 40865 | This order is being commissioned, and it is not currently supported to close the position |
| 40866 | You are currently a trader, please close the position under the current order |
| 40867 | Currently the maximum number of positions that can be closed is {0}, please go to the current order to close the position if the amount exceeds |
| 40868 | You are currently a trader and currently do not support liquidation through planned orders |
| 40869 | You are currently a trader and currently do not support modification of leverage |
| 40871 | The leverage does not meet the configuration, and you cannot become a trader |
| 40872 | Failed to adjust position, currently holding position or order or plan order |
| 40873 | The account has a margin and needs to be transferred out |
| 40874 | Whole position mode does not support automatic margin call |
| 40875 | Whole position mode does not support margin adjustment |
| 40877 | Too many follow-up orders |
| 40878 | The contract index data is abnormal. In order to avoid causing your loss, please try again later. |
| 40879 | The risk is being processed, and the funds cannot be adjusted. |
| 40880 | The risk is being processed and the leverage cannot be adjusted. |
| 40889 | The plan order of this contract has reached the upper limit |
| 40890 | The order of stop-profit and stop-loss for this contract has reached the upper limit |
| 40891 | Insufficient position, can not set take profit or stop loss |
| 40892 | Failed to place the order, the minimum number of positions opened by the trader is {0} |
| 40893 | Unable to update the leverage factor of this position, there is not enough margin! |
| 40895 | The preset price does not match the order/execution price |
| 40896 | The default stop profit and stop loss has been partially fulfilled and cannot be modified |
| 40897 | The system experience gold account does not exist |
| 40898 | The system experience gold account balance is insufficient |
| 40899 | The number of stored users exceeds the limit |
| 40900 | The system experience gold account is inconsistent |
| 40901 | The contract experience fund balance is insufficient |
| 40902 | Future time is not allowed |
| 40903 | Failed to obtain leverage information |
| 40904 | Failed to collect funds |
| 40905 | Failed to collect user funds |
| 40906 | Failed to pay user funds |
| 40907 | The payment cannot be transferred |
| 40908 | Concurrent operation failed |
| 40909 | Transfer processing |
| 40910 | Operation timed out |
| 40911 | Request timestamp expired |
| 40914 | Trader the maximum leverage can use is {0} |
| 40915 | Long position take profit price please > mark price |
| 40916 | The business of this account has been restricted |
| 40917 | Stop price for long positions please < mark price {0} |
| 40918 | Traders open positions with orders too frequently |
| 40919 | This function is not open yet |
| 40920 | Position or order exists, the position mode cannot be switched |
| 40922 | Only work order modifications are allowed |
| 40923 | Order size and price have not changed |
| 40925 | price or size must be passed in together |
| 40926 | Your identity authentication is still under review. Please wait for the review to pass before trying this function again |
| 40928 | reduceOnly will only reduce the positions. Please cancel or modify the original pending orders before making order again |
| 40929 | TraderPro Maximum leverage is {0}X |
| 40930 | The remaining quantity for your normal order is {0}{1}, and the quantity for post only order is {2}{3} |
| 40931 | Trigger the risk control of position closing , prohibiting position closing |
| 41101 | Param {0} error |
| 41113 | Symbol is offline |
| 41114 | The current trading pair is under maintenance, please refer to the official announcement for the opening time |
| 41117 | {0} selling price cannot be lower than {1} |
| 41118 | {0} buy-in price cannot be higher than {1} |
| 42072 | Param endTime cannot be earlier than startTime |
| 43001 | The order does not exist |
| 43002 | Pending order failed |
| 43003 | Pending order failed |
| 43004 | There is no order to cancel |
| 43005 | Exceed the maximum number of orders |
| 43006 | The order quantity is less than the minimum transaction quantity |
| 43007 | The order quantity is greater than the maximum transaction quantity |
| 43008 | The current order price cannot be less than {0}{1} |
| 43009 | The current order price exceeds the limit {0}{1} |
| 43010 | The transaction amount cannot be less than {0}{1} |
| 43012 | Insufficient balance |
| 43022 | Failed to trigger the default stop loss |
| 43027 | The minimum order value {0} is not met |
| 43028 | Please enter an integer multiple of {0} for price |
| 43112 | The account is liquidated |
| 43118 | clientOrderId duplicate |
| 43119 | Trading is not open |
| 43120 | Symbol is not open trade |
| 43122 | The purchase limit of this currency is {0}, and there is still {1} left |
| 43123 | param error {0} |
| 43135 | Loan risk control check failed |
| 45001 | Unknown error |
| 45002 | Insufficient asset |
| 45003 | Insufficient position |
| 45004 | Insufficient lock-in asset |
| 45005 | Insufficient available positions |
| 45006 | Insufficient position |
| 45007 | Insufficient lock position |
| 45008 | No assets |
| 45009 | The account is at risk and cannot perform trades temporarily |
| 45010 | The number of orders cannot exceed the maximum amount of the corresponding leverage |
| 45011 | Order remaining volume < Current transaction volume |
| 45012 | Remaining volume of position < Volume of current transaction |
| 45013 | The number of open orders < Current transaction volume |
| 45014 | Position does not exist during opening |
| 45017 | Settlement or the coin for transaction configuration not found |
| 45018 | In the case of a netting, you cannot have a liquidation order |
| 45019 | Account does not exist |
| 45020 | Liquidation can only occur under two-way positions |
| 45023 | Error creating order |
| 45024 | Cancel order error |
| 45025 | The currency pair does not support the currency as a margin |
| 45026 | Please check that the correct delegateType is used |
| 45031 | The order is finalized |
| 45035 | Price step mismatch |
| 45043 | Due to settlement or maintenance reasons, the trade is suspended |
| 45044 | Leverage is not within the suitable range after adjustment |
| 45045 | Exceeds the maximum possible leverage |
| 45047 | Reduce the leverage and the amount of additional margin is incorrect |
| 45051 | Execution price parameter verification is abnormal |
| 45052 | Trigger price parameter verification anbormal |
| 45054 | No change in leverage |
| 45055 | The current order status cannot be cancelled |
| 45056 | The current order type cannot be cancelled |
| 45057 | The order does not exist! |
| 45060 | TP price of long position > Current price {0} |
| 45062 | SL price of long position < Current price {0} |
| 45064 | TP price of long position > order price {0} |
| 45065 | TP price of short position < order price {0} |
| 45066 | SL price of long position < order price {0} |
| 45067 | SL price of short position > order price {0} |
| 45068 | There is no position temporarily, and the order of TP and SL cannot be carried out |
| 45075 | The user already has an ongoing copy trade |
| 45082 | Copy trade number error |
| 45089 | You are currently copy trading, leverage cannot be changed |
| 45091 | Too many tracking orders |
| 45097 | There is currently an order or a limit order, and the leverage cannot be adjusted |
| 45098 | You are currently a trader and cannot be switched to the full position mode |
| 45099 | When there are different coins, it cannot be adjusted to Isolated Margin mode |
| 45100 | When a one-way position is held, it cannot be adjusted to the Isolated Margin mode |
| 45101 | In Isolated Margin mode, it cannot be adjusted to a one-way position |
| 45102 | In the full position mode, the automatic margin call cannot be adjusted |
| 45103 | Failed to place the order, the maximum amount of single flash opening position is %s |
| 45104 | Failed to place the order, the maximum amount of single flash closing position is %s |
| 45106 | copy trade liquidation has been processed |
| 45107 | API is restricted to open positions. If you have any questions, please contact our customer service |
| 45108 | API is restricted to close position. If you have any questions, please contact our customer service |
| 45109 | The current account is a two-way position |
| 45110 | less than the minimum amount {0} USDT |
| 45111 | less than the minimum order quantity {0} |
| 45112 | more than the maximum order quantity |
| 45113 | Maximum order value limit triggered |
| 45114 | The minimum order requirement is not met |
| 45115 | The price you enter should be a multiple of {0}{1} |
| 45116 | The count of positions hold by the account exceeds the maximum count {0} |
| 45117 | Currently holding positions or orders, the margin mode cannot be adjusted |
| 45118 | Reached the upper limit of the order of transactions (the current number of order + the current number of orders) {0} |
| 45119 | This symbol does not support position opening operation |
| 45121 | The reasonable mark price deviates too much from the market, and your current leveraged position opening risk is high |
| 45122 | Short position stop loss price please > mark price {0} |
| 45123 | Insufficient availability, currently only market orders can be placed |
| 45124 | Please edit and submit again. |
| 45125 | Order cancellation is unavailable for inactive orders. Please cancel parent order and place a new order. |
| 45126 | Order cancellation is unavailable for inactive orders. Please cancel parent order and place a new order. |
| 45127 | Position brackets disabled TP SL |
| 45128 | Position brackets disabled modify qty |
| 45129 | Cancel order is too frequent, the same orderId is only allowed to be canceled once in a second |
| 45133 | Exceeded the maximum quantity of contract orders: {0} {1} |
| 45134 | The order {0}:{1} have filled or cancelled |
| 45135 | The take-profit price for short positions must be less than the mark price: {0}. |
| 46013 | This symbol limits the selling amount{0}Remaining{0} |
| 50018 | The price must be 0 or higher |
| 50060 | Duplicated clientOid |
| 50101 | withdraw address is not in addressBook |
| 59014 | Parameter precision exception |
| 70220 | Insufficient liquidity in the market, please operate later |
| 70221 | The current currency is {0}, the net purchase value is limited to {1} USD, and you can also purchase {3} with a net purchase value of {2} USD. |
| 70222 | The current currency is {0}, the net purchase quantity is limited to {1}, and the net purchase quantity is also {2} |
| 70223 | Exceeding the maximum number of orders for total trading pairs: {0} |
| 70224 | This currency has a selling limit of {0}, leaving {1} |
| 70225 | This currency has a buying limit of {0}, leaving {1} |
| 70226 | The current maximum amount of coins that can be withdrawn or transferred out is {0}. If you want to withdraw or transfer all coins, please confirm that all spot orders have been ended. |
| 70227 | The user does not allow to place order |
| 70228 | The operation is too frequent, please try again later. |
| 70229 | Place order error |
| 95005 | The LTV for ins loan has exceeded the limit, and opening contracts is prohibited |
| 95006 | The LTV for ins loan has exceeded the limit, and spot buying is prohibited |
| 95007 | Ins loan is not support this spot trading pair. |
| 95008 | Ins loan is not support futures trading. |
| 95009 | Ins loan is not support this margin trading pair. |
| 95010 | Your entered subaccount UID is already bound to another risk unit. |
| 95011 | Parameter validation failed:{0} |
| 95012 | The LTV data for ins loan users is incorrect. For more details, please contact customer service. |
| 500024 | The trading pair does not exist |