# H1
## H2
### H3
#### H4
##### H5
###### H6

This is a *test* of **markdown**.

![Image of Price](https://greatgoodfortune.net/img/%E6%9C%8D%E5%8B%99%E5%83%B9%E7%9B%AE.svg)

```
import pandas as pd
df=pd.read_csv('data/tx1998_2023.csv', parse_dates=['Date'])

df['Profit']=0
df['Position']=0
df['MA20']= df['Close'].rolling(20).mean()
df['MA50']= df['Close'].rolling(50).mean()
df['ATR']=0

df.iloc[0, 5]
日, 契, 開, 高, 低, 收, 利, 部, MA20, MA50, ATR = 0,1,2,3,4,5,6,7,8,9,10

for i in range(1, 20): #df.shape[0]):
    df.iloc[i, ATR] = max(df.iloc[i, 高]-df.iloc[i, 低],
                          abs(df.iloc[i, 高]-df.iloc[i-1, 收]),
                          abs(df.iloc[i, 低]-df.iloc[i-1, 收]))
    if df.iloc[i+1, 高] > df.iloc[i, 高]:
        print(df.iloc[i+1, 日], '過前日高', df.iloc[i, 高], '<--', df.iloc[i+1, 高])
```
