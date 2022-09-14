# GoogleTrendsData

import pandas as pd
import numpy as np

df = pd.read_csv(r'C:\Users\ELIZABETH\Desktop\EON LABS\monthly_data.csv')

df['time_month'] = pd.to_datetime(df['time_month'], unit='s')

df.dtypes

time_month     datetime64[ns]
value_month             int64
date                   object
dtype: object

#resampling the value to hourly interval, applying a function (mean in this case) and interpolating the value_month
df_rs = df.set_index('time_month').resample('H').mean().interpolate()
df_rs

df_rs.to_csv(r'C:\Users\ELIZABETH\Desktop\EON LABS\monthly_to_hourly.csv')[monthly_to_hourly.csv](https://github.com/riyapothen/GoogleTrendsData/files/9568682/monthly_to_hourly.csv)
