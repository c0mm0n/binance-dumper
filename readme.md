# binance-dumper  
Script that attempts to sell the position at best price during the first candle when trading starts on Binance.  
  
# Requirements  
Node v10.15+  

# Instructions  
1) Install npm depedencies.  
```npm install```  
2) Configure script parameters. (See below)
3) Run the script  
```npm start```  

# Script Configuration
Configuration object *CONFIG* can be found at the top of *index.js* file. Script is configurable using following parameters:  

Name | Type | Description
-----| ---- | -----------
apiKey | STRING | Your Binance API Key.  
apiSecret | STRING | Your Binance API Secret.  
symbol | STRING | Pair that you want to trade (ex. "BTCUSDT").  
tradingStartTime | NUMBER | start time (in miliseconds) when trading is suppose to start.  
sellQuantity | DECIMAL | The size of your position you are trying to sell.  
minSellPrice | DECIMAL | The minimum price. Script won't place orders below this price.  
startingPrice | DECIMAL | The first order price. Script uses this price to place the first order when trading opens and order book is empty.  
priceDelta | DECIMAL | Price difference (expressed in percentage) between order price and current best price when script adjusts order price to match current bid. Example: If we set *priceDelta = 0.03* and current order price is 100$, when best bid price moves below 97$ (3%), the old order will be cancelled and new order will be created with the price set to current bid.  