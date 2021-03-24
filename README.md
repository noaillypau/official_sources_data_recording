# official_sources_data_recording

Consist on jupyter notebook for each data source, in wich 1min ohlc data is recorder, and tick data also if it is available.

Data is scrapped directly from the broker, to avoid any backtest/live diferences.

Currently support mt5 (for every thing except crypto) and Bybit.

In the Bybit notebook you can see an example of 1min ohlc data reconstitution from trades tick data, with more informations about the trades within the 1min candlesticks.

Plan is to add FTX and Binance soon.

The is also a data manager within `dataManager.py`.

## dataManager

Instance dataManager with type of asset. (Native attributes of DataManager)
```python
from dataManager import DataManager
dataManager = DataManager(DataManager.Crypto)
```

Create a dataset and extract data frame
```python
dataset = BYBIT_PREMIUM_OHLC_BTCUSD_1min
df = dataManager.get_df(dataManager.VANTAGEFX_PRICE_EURUSD_1min, 
                        start_year=2005,
                        start_month=5,
                        end_year=2008,
                        end_month=9, 
                        add_date=True)
```

## Todo

- [ ] add ftx notebook
- [ ] add binance notebook
- [ ] parse the main path (here D://Trading/Data) as a parameter for notebooks and dataManager (stored in a yml config file)
