# YchartsWebCrawler
Get Historical Stock Fundemental Data from YCharts.com

## Usage
1). Download GetFundamentalData.ipynb  
2). Run the notebook  
3). Choose features from  
```python
features = ['market_cap', 'pe_ratio', 'ps_ratio', 'price_to_book_value',
            'ev_ebitda', 'ev_ebit', 'ev_revenues', 'ev_free_cash_flow',
            'eps', 'ebitda', 'revenues_growth', 'profit_margin', 'cash_on_hand',
            'price_to_cash_flow_ttm', 'peg_ratio', 'ev_assets']
```
4). Call GetHistoricalFundamentalData with stock price, start date, end date, and feature(s) to get data.
## Note
1) Not all features are time-consistent (i.g. some features are weekly updated, some features are quarterly updated, etc.)  
2) If the function doesn't work appropriately (i.g. return Nan values or raise an exception), try to update your 'cookie' in the 'header'.
3) The function traces the data provided by the YCharts.com, and the return data is consistent with the data on the website.
## Examp
```python
stock = 'NFLX'
start = '03/03/2010'
end   = '03/03/2015'
features = ['eps', 'ebitda', 'revenues_growth', 'profit_margin','ev_assets']
df = GetHistoricalFundamentalData(stock, start, end, features)
df
```
