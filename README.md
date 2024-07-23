# AlphaVantage
API for getting historical options data.

https://www.alphavantage.co/documentation/#options

https://www.alphavantage.co/query?function=HISTORICAL_OPTIONS&symbol=NVDA&date=2024-07-01&apikey=78JCJ98MOWJ50FMT


## Historical Options 

This API returns the full historical options chain for a specific symbol on a specific date, covering 15+ years of history. Implied volatility (IV) and common Greeks (e.g., delta, gamma, theta, vega, rho) are also returned. Option chains are sorted by expiration dates in chronological order. Within the same expiration date, contracts are sorted by strike prices from low to high.


API Parameters
❚ Required: function

The time series of your choice. In this case, function=HISTORICAL_OPTIONS

❚ Required: symbol

The name of the equity of your choice. For example: symbol=IBM

❚ Optional: date

By default, the date parameter is not set and the API will return data for the previous trading session. Any date later than 2008-01-01 is accepted. For example, date=2017-11-15.

❚ Optional: datatype

By default, datatype=json. Strings json and csv are accepted with the following specifications: json returns the options data in JSON format; csv returns the data as a CSV (comma separated value) file.

❚ Required: apikey

Your API key. Claim your free API key here.


Example (click for JSON output)
When the date paramter is not set, data from the previous trading session is returned
https://www.alphavantage.co/query?function=HISTORICAL_OPTIONS&symbol=IBM&apikey=demo

Specify a date to retrieve options data for any trading day in the past 15+ years (since 2018-01-01)
https://www.alphavantage.co/query?function=HISTORICAL_OPTIONS&symbol=IBM&date=2017-11-15&apikey=demo

Downloadable CSV file:
https://www.alphavantage.co/query?function=HISTORICAL_OPTIONS&symbol=IBM&date=2017-11-15&apikey=demo&datatype=csv

```python
import requests

# replace the "demo" apikey below with your own key from https://www.alphavantage.co/support/#api-key
url = 'https://www.alphavantage.co/query?function=HISTORICAL_OPTIONS&symbol=IBM&apikey=demo'
r = requests.get(url)
data = r.json()

print(data)
```


