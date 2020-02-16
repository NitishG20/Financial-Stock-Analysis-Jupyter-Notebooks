
Module 1
========

### Welcome to the Answer notebook for Module 1 ! These notebooks have
been provided to code and solve all the queries asked in the modules.

This environment has all the necessary libraries pre-installed, and all
the Stock, Commodities and Index data files available at the following
location -

The problem statements and their corresponding answers are expected to be in the following format -
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

#——————————————————————————————————————————————————————————————————–#

Query 1.1
~~~~~~~~~

Import the csv file of the stock of your choosing using ‘pd.read_csv()’
function into a dataframe. Shares of a company can be offered in more
than one category. The category of a stock is indicated in the ‘Series’
column. If the csv file has data on more than one category, the ‘Date’
column will have repeating values. To avoid repetitions in the date,
remove all the rows where ‘Series’ column is NOT ‘EQ’. Analyze and
understand each column properly. You’d find the head(), tail() and
describe() functions to be immensely useful for exploration. You’re free
to carry out any other exploration of your own.

.. code:: ipython3

    #The solution code should start right after the query statement, for example -
    import numpy as np 
    import pandas as pd
    import warnings
    warnings.filterwarnings('ignore')
    df = pd.read_csv('PNB.csv')
    print(df.head())
    print(df.tail())
    df.describe()


.. parsed-literal::

      Symbol Series         Date  Prev Close  Open Price  High Price  Low Price  \
    0    PNB     EQ  15-May-2017      169.15      169.95      171.30      166.2   
    1    PNB     EQ  16-May-2017      166.80      167.35      178.00      164.8   
    2    PNB     EQ  17-May-2017      174.15      173.00      173.10      164.3   
    3    PNB     EQ  18-May-2017      165.05      163.40      164.40      157.9   
    4    PNB     EQ  19-May-2017      158.50      159.50      162.25      154.1   
    
       Last Price  Close Price  Average Price  Total Traded Quantity  \
    0      166.85       166.80         168.94                7476618   
    1      173.20       174.15         173.13               51532461   
    2      164.80       165.05         167.27               26536944   
    3      158.25       158.50         161.06               13905573   
    4      155.20       155.20         157.59               16311602   
    
           Turnover  No. of Trades  Deliverable Qty  % Dly Qt to Traded Qty  
    0  1.263123e+09          41641          1352589                   18.09  
    1  8.921904e+09         254027          5804867                   11.26  
    2  4.438942e+09         116512          7037498                   26.52  
    3  2.239613e+09          76746          3245443                   23.34  
    4  2.570540e+09          82394          2816963                   17.27  
        Symbol Series         Date  Prev Close  Open Price  High Price  Low Price  \
    489    PNB     EQ  07-May-2019       86.25       86.70       87.15      83.40   
    490    PNB     EQ  08-May-2019       83.95       83.75       85.40      83.25   
    491    PNB     EQ  09-May-2019       83.95       84.10       85.35      82.80   
    492    PNB     EQ  10-May-2019       84.25       85.00       87.25      84.40   
    493    PNB     EQ  13-May-2019       86.25       86.15       86.20      79.05   
    
         Last Price  Close Price  Average Price  Total Traded Quantity  \
    489       84.05        83.95          85.62               16356567   
    490       84.05        83.95          84.43               23380690   
    491       84.50        84.25          84.30               22934344   
    492       86.00        86.25          85.53               21821500   
    493       79.90        79.80          82.13               34293332   
    
             Turnover  No. of Trades  Deliverable Qty  % Dly Qt to Traded Qty  
    489  1.400418e+09          37679          2333933                   14.27  
    490  1.974095e+09          52244          2674859                   11.44  
    491  1.933317e+09          44704          2025433                    8.83  
    492  1.866353e+09          44879          1950720                    8.94  
    493  2.816529e+09          88162          7102109                   20.71  




.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>Prev Close</th>
          <th>Open Price</th>
          <th>High Price</th>
          <th>Low Price</th>
          <th>Last Price</th>
          <th>Close Price</th>
          <th>Average Price</th>
          <th>Total Traded Quantity</th>
          <th>Turnover</th>
          <th>No. of Trades</th>
          <th>Deliverable Qty</th>
          <th>% Dly Qt to Traded Qty</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>count</th>
          <td>494.000000</td>
          <td>494.000000</td>
          <td>494.000000</td>
          <td>494.000000</td>
          <td>494.000000</td>
          <td>494.00000</td>
          <td>494.000000</td>
          <td>4.940000e+02</td>
          <td>4.940000e+02</td>
          <td>494.000000</td>
          <td>4.940000e+02</td>
          <td>494.000000</td>
        </tr>
        <tr>
          <th>mean</th>
          <td>112.380870</td>
          <td>112.576822</td>
          <td>114.621255</td>
          <td>110.243623</td>
          <td>112.187551</td>
          <td>112.20000</td>
          <td>112.462085</td>
          <td>2.515651e+07</td>
          <td>2.671164e+09</td>
          <td>74657.987854</td>
          <td>4.169411e+06</td>
          <td>17.631721</td>
        </tr>
        <tr>
          <th>std</th>
          <td>40.026359</td>
          <td>40.144154</td>
          <td>41.033817</td>
          <td>39.184032</td>
          <td>40.033928</td>
          <td>39.97115</td>
          <td>40.067790</td>
          <td>2.501765e+07</td>
          <td>3.160705e+09</td>
          <td>73820.770037</td>
          <td>4.510557e+06</td>
          <td>7.346969</td>
        </tr>
        <tr>
          <th>min</th>
          <td>59.700000</td>
          <td>60.000000</td>
          <td>63.400000</td>
          <td>58.450000</td>
          <td>59.750000</td>
          <td>59.70000</td>
          <td>60.730000</td>
          <td>1.148287e+06</td>
          <td>1.492829e+08</td>
          <td>6684.000000</td>
          <td>3.466790e+05</td>
          <td>5.180000</td>
        </tr>
        <tr>
          <th>25%</th>
          <td>79.300000</td>
          <td>79.512500</td>
          <td>80.850000</td>
          <td>78.112500</td>
          <td>79.275000</td>
          <td>79.30000</td>
          <td>79.517500</td>
          <td>1.187260e+07</td>
          <td>1.275810e+09</td>
          <td>39754.250000</td>
          <td>1.912565e+06</td>
          <td>12.650000</td>
        </tr>
        <tr>
          <th>50%</th>
          <td>93.400000</td>
          <td>93.775000</td>
          <td>94.975000</td>
          <td>92.350000</td>
          <td>93.325000</td>
          <td>93.37500</td>
          <td>93.625000</td>
          <td>1.896336e+07</td>
          <td>1.854954e+09</td>
          <td>54358.000000</td>
          <td>2.932769e+06</td>
          <td>16.145000</td>
        </tr>
        <tr>
          <th>75%</th>
          <td>147.450000</td>
          <td>148.400000</td>
          <td>150.250000</td>
          <td>144.937500</td>
          <td>147.137500</td>
          <td>147.40000</td>
          <td>147.970000</td>
          <td>2.825566e+07</td>
          <td>2.818940e+09</td>
          <td>80766.500000</td>
          <td>4.841530e+06</td>
          <td>20.817500</td>
        </tr>
        <tr>
          <th>max</th>
          <td>213.600000</td>
          <td>214.000000</td>
          <td>231.450000</td>
          <td>201.100000</td>
          <td>218.000000</td>
          <td>213.60000</td>
          <td>213.210000</td>
          <td>2.107817e+08</td>
          <td>3.137858e+10</td>
          <td>626019.000000</td>
          <td>5.128026e+07</td>
          <td>53.840000</td>
        </tr>
      </tbody>
    </table>
    </div>



Query 1.2
~~~~~~~~~

Calculate the maximum, minimum and mean price for the last 90 days.
(price=Closing Price unless stated otherwise)

.. code:: ipython3

    data=np.array(df['Close Price'])
    data = data[-90:]
    print(data)
    print(np.max(data))
    print(np.min(data))
    print(np.mean(data))


.. parsed-literal::

    [78.1  79.8  77.85 77.85 81.3  80.55 81.7  80.7  81.25 80.65 82.5  81.95
     84.25 84.55 82.85 80.25 78.6  77.75 78.1  76.6  76.1  77.3  77.25 77.5
     73.9  73.15 73.4  75.2  75.65 71.2  70.85 71.35 69.45 72.25 70.05 69.
     69.95 71.1  73.15 73.2  73.5  71.85 71.5  72.3  76.65 82.65 82.4  85.45
     83.8  85.85 85.4  84.85 84.45 86.05 86.65 90.5  93.55 91.55 90.3  92.5
     93.4  95.35 95.5  97.5  98.3  94.45 93.65 93.1  93.1  94.35 93.35 92.7
     93.35 93.85 92.8  90.05 86.65 87.2  88.35 86.75 88.15 84.9  86.1  87.15
     86.25 83.95 83.95 84.25 86.25 79.8 ]
    98.3
    69.0
    82.71555555555557


Query 1.3
~~~~~~~~~

Analyse the data types for each column of the dataframe. Pandas knows
how to deal with dates in an intelligent manner. But to make use of
Pandas functionality for dates, you need to ensure that the column is of
type ‘datetime64(ns)’. Change the date column from ‘object’ type to
‘datetime64(ns)’ for future convenience. See what happens if you
subtract the minimum value of the date column from the maximum value.

.. code:: ipython3

    print(df.dtypes)
    df['Date']=pd.to_datetime(df.Date)
    print("\n\nChanged the date column from 'object' type to 'datetime64(ns)''")
    print(df.dtypes)


.. parsed-literal::

    Symbol                     object
    Series                     object
    Date                       object
    Prev Close                float64
    Open Price                float64
    High Price                float64
    Low Price                 float64
    Last Price                float64
    Close Price               float64
    Average Price             float64
    Total Traded Quantity       int64
    Turnover                  float64
    No. of Trades               int64
    Deliverable Qty             int64
    % Dly Qt to Traded Qty    float64
    dtype: object
    
    
    Changed the date column from 'object' type to 'datetime64(ns)''
    Symbol                            object
    Series                            object
    Date                      datetime64[ns]
    Prev Close                       float64
    Open Price                       float64
    High Price                       float64
    Low Price                        float64
    Last Price                       float64
    Close Price                      float64
    Average Price                    float64
    Total Traded Quantity              int64
    Turnover                         float64
    No. of Trades                      int64
    Deliverable Qty                    int64
    % Dly Qt to Traded Qty           float64
    dtype: object


Query 1.4
~~~~~~~~~

In a separate array , calculate the monthwise VWAP (Volume Weighted
Average Price ) of the stock. ( VWAP = sum(price*volume)/sum(volume) )
To know more about VWAP , visit - VWAP definition {Hint : Create a new
dataframe column ‘Month’. The values for this column can be derived from
the ‘Date” column by using appropriate pandas functions. Similarly,
create a column ‘Year’ and initialize it. Then use the ‘groupby()’
function by month and year. Finally, calculate the vwap value for each
month (i.e. for each group created).

.. code:: ipython3

    df['Month']=pd.Series([i.month_name() for i in df['Date']])
    df['Year']=pd.Series([i.year for i in df['Date']])
    
    new = df
    new['price*volume']=new['Close Price']*new['Total Traded Quantity']
    new=new.loc[:, ['Month', 'Year','price*volume', 'Total Traded Quantity']].groupby(['Month', 'Year'])
    new=new['price*volume', 'Total Traded Quantity'].agg(np.sum)
    new['VWAP']=new['price*volume']/new['Total Traded Quantity']
    print(new.loc[:, ['VWAP']])


.. parsed-literal::

                          VWAP
    Month     Year            
    April     2018   98.452684
              2019   92.630680
    August    2017  147.583982
              2018   84.404688
    December  2017  173.158001
              2018   73.083889
    February  2018  119.843376
              2019   72.407841
    January   2018  177.425422
              2019   80.117278
    July      2017  152.844298
              2018   79.282495
    June      2017  146.144594
              2018   84.127327
    March     2018   97.928249
              2019   88.435446
    May       2017  158.529155
              2018   82.944949
              2019   84.371657
    November  2017  193.098141
              2018   70.891962
    October   2017  193.005039
              2018   66.537495
    September 2017  139.951927
              2018   74.282560


Query 1.5
~~~~~~~~~

Write a function to calculate the average price over the last N days of
the stock price data where N is a user defined parameter. Write a second
function to calculate the profit/loss percentage over the last N days.
Calculate the average price AND the profit/loss percentages over the
course of last - 1 week, 2 weeks, 1 month, 3 months, 6 months and 1
year. {Note : Profit/Loss percentage between N days is the percentage
change between the closing prices of the 2 days }

.. code:: ipython3

    def avg_price_lastNdays(df, N):
        X=np.array(df['Close Price'])    
        return np.average(X[-N:])#.agg(np.mean)
    def profit_loss_Ndays(df, N):
        X=np.array(df['Close Price'])
        return np.absolute(X[-1]-X[-N])*100/X[-N]
    index = df.columns.get_loc("Close Price")
    print("Profit/Loss percentage over 1 week = % 0.2f%%" %(profit_loss_Ndays(df, 7)))
    print("Profit/Loss percentage over 2 weeks = % 0.2f%%" %(profit_loss_Ndays(df, 14)))
    print("Profit/Loss percentage over 1 month = % 0.2f%%" %(profit_loss_Ndays(df, 30)))
    print("Profit/Loss percentage over 3 months = % 0.2f%%" %(profit_loss_Ndays(df, 90)))
    print("Profit/Loss percentage over 6 months = % 0.2f%%" %(profit_loss_Ndays(df, 180)))
    print("Profit/Loss percentage over 1 Year = % 0.2f%%" %(profit_loss_Ndays(df, 365)))
    print("Average Price over 1 week = % 0.2f" %(avg_price_lastNdays(df, 7)))
    print("Average Price over 2 weeks = % 0.2f" %(avg_price_lastNdays(df, 14)))
    print("Average Price over 1 month = % 0.2f" %(avg_price_lastNdays(df, 30)))
    print("Average Price over 3 months = % 0.2f" %(avg_price_lastNdays(df, 90)))
    print("Average Price over 6 months = % 0.2f" %(avg_price_lastNdays(df, 180)))
    print("Average Price over 1 Year = % 0.2f" %(avg_price_lastNdays(df, 365)))


.. parsed-literal::

    Profit/Loss percentage over 1 week =  8.43%
    Profit/Loss percentage over 2 weeks =  7.91%
    Profit/Loss percentage over 1 month =  14.56%
    Profit/Loss percentage over 3 months =  2.18%
    Profit/Loss percentage over 6 months =  0.13%
    Profit/Loss percentage over 1 Year =  58.18%
    Average Price over 1 week =  84.51
    Average Price over 2 weeks =  85.69
    Average Price over 1 month =  90.15
    Average Price over 3 months =  82.72
    Average Price over 6 months =  77.99
    Average Price over 1 Year =  98.09


Query 1.6
~~~~~~~~~

Add a column ‘Day_Perc_Change’ where the values are the daily change in
percentages i.e. the percentage change between 2 consecutive day’s
closing prices. Instead of using the basic mathematical formula for
computing the same, use ‘pct_change()’ function provided by Pandas for
dataframes. You will note that the first entry of the column will have a
‘Nan’ value. Why does this happen? Either remove the first row, or set
the entry to 0 before proceeding.

.. code:: ipython3

    df=df.drop(columns=['price*volume'])
    Z = df['Close Price'].pct_change()
    Z[0]=0
    df['Day_Perc_Change']=Z
    df.head()




.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>Symbol</th>
          <th>Series</th>
          <th>Date</th>
          <th>Prev Close</th>
          <th>Open Price</th>
          <th>High Price</th>
          <th>Low Price</th>
          <th>Last Price</th>
          <th>Close Price</th>
          <th>Average Price</th>
          <th>Total Traded Quantity</th>
          <th>Turnover</th>
          <th>No. of Trades</th>
          <th>Deliverable Qty</th>
          <th>% Dly Qt to Traded Qty</th>
          <th>Month</th>
          <th>Year</th>
          <th>Day_Perc_Change</th>
          <th>Trend</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-15</td>
          <td>169.15</td>
          <td>169.95</td>
          <td>171.30</td>
          <td>166.2</td>
          <td>166.85</td>
          <td>166.80</td>
          <td>168.94</td>
          <td>7476618</td>
          <td>1.263123e+09</td>
          <td>41641</td>
          <td>1352589</td>
          <td>18.09</td>
          <td>May</td>
          <td>2017</td>
          <td>0.000000</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>1</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-16</td>
          <td>166.80</td>
          <td>167.35</td>
          <td>178.00</td>
          <td>164.8</td>
          <td>173.20</td>
          <td>174.15</td>
          <td>173.13</td>
          <td>51532461</td>
          <td>8.921904e+09</td>
          <td>254027</td>
          <td>5804867</td>
          <td>11.26</td>
          <td>May</td>
          <td>2017</td>
          <td>0.044065</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>2</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-17</td>
          <td>174.15</td>
          <td>173.00</td>
          <td>173.10</td>
          <td>164.3</td>
          <td>164.80</td>
          <td>165.05</td>
          <td>167.27</td>
          <td>26536944</td>
          <td>4.438942e+09</td>
          <td>116512</td>
          <td>7037498</td>
          <td>26.52</td>
          <td>May</td>
          <td>2017</td>
          <td>-0.052254</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>3</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-18</td>
          <td>165.05</td>
          <td>163.40</td>
          <td>164.40</td>
          <td>157.9</td>
          <td>158.25</td>
          <td>158.50</td>
          <td>161.06</td>
          <td>13905573</td>
          <td>2.239613e+09</td>
          <td>76746</td>
          <td>3245443</td>
          <td>23.34</td>
          <td>May</td>
          <td>2017</td>
          <td>-0.039685</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>4</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-19</td>
          <td>158.50</td>
          <td>159.50</td>
          <td>162.25</td>
          <td>154.1</td>
          <td>155.20</td>
          <td>155.20</td>
          <td>157.59</td>
          <td>16311602</td>
          <td>2.570540e+09</td>
          <td>82394</td>
          <td>2816963</td>
          <td>17.27</td>
          <td>May</td>
          <td>2017</td>
          <td>-0.020820</td>
          <td>Slight or No change</td>
        </tr>
      </tbody>
    </table>
    </div>



Query 1.7
~~~~~~~~~

Add another column ‘Trend’ whose values are: ‘Slight or No change’ for
‘Day_Perc_Change’ in between -0.5 and 0.5 ‘Slight positive’ for
‘Day_Perc_Change’ in between 0.5 and 1 ‘Slight negative’ for
‘Day_Perc_Change’ in between -0.5 and -1 ‘Positive’ for
‘Day_Perc_Change’ in between 1 and 3 ‘Negative’ for ‘Day_Perc_Change’ in
between -1 and -3 ‘Among top gainers’ for ‘Day_Perc_Change’ in between 3
and 7 ‘Among top losers’ for ‘Day_Perc_Change’ in between -3 and -7
‘Bull run’ for ‘Day_Perc_Change’ >7 ‘Bear drop’ for ‘Day_Perc_Change’
<-7

.. code:: ipython3

    def getTrend(n):
        if -0.5<n<=0.5:
            return 'Slight or No change'
        if 0.5<n<=1:
            return 'Slight negative'
        if 1<n<=3:
            return 'Positive'
        if -3<n<=-1:
            return 'Negative'
        if 3<n<=7:
            return 'Among top gainers'
        if -7<n<=-3:
            return 'Among top losers'
        if n>7:
            return 'Bull run'
        if n<-7:
            return 'Bear drop'     
    df['Trend']=pd.Series([getTrend(i) for i in df['Day_Perc_Change']])
    df.head()




.. raw:: html

    <div>
    <style scoped>
        .dataframe tbody tr th:only-of-type {
            vertical-align: middle;
        }
    
        .dataframe tbody tr th {
            vertical-align: top;
        }
    
        .dataframe thead th {
            text-align: right;
        }
    </style>
    <table border="1" class="dataframe">
      <thead>
        <tr style="text-align: right;">
          <th></th>
          <th>Symbol</th>
          <th>Series</th>
          <th>Date</th>
          <th>Prev Close</th>
          <th>Open Price</th>
          <th>High Price</th>
          <th>Low Price</th>
          <th>Last Price</th>
          <th>Close Price</th>
          <th>Average Price</th>
          <th>Total Traded Quantity</th>
          <th>Turnover</th>
          <th>No. of Trades</th>
          <th>Deliverable Qty</th>
          <th>% Dly Qt to Traded Qty</th>
          <th>Month</th>
          <th>Year</th>
          <th>Day_Perc_Change</th>
          <th>Trend</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th>0</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-15</td>
          <td>169.15</td>
          <td>169.95</td>
          <td>171.30</td>
          <td>166.2</td>
          <td>166.85</td>
          <td>166.80</td>
          <td>168.94</td>
          <td>7476618</td>
          <td>1.263123e+09</td>
          <td>41641</td>
          <td>1352589</td>
          <td>18.09</td>
          <td>May</td>
          <td>2017</td>
          <td>0.000000</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>1</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-16</td>
          <td>166.80</td>
          <td>167.35</td>
          <td>178.00</td>
          <td>164.8</td>
          <td>173.20</td>
          <td>174.15</td>
          <td>173.13</td>
          <td>51532461</td>
          <td>8.921904e+09</td>
          <td>254027</td>
          <td>5804867</td>
          <td>11.26</td>
          <td>May</td>
          <td>2017</td>
          <td>0.044065</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>2</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-17</td>
          <td>174.15</td>
          <td>173.00</td>
          <td>173.10</td>
          <td>164.3</td>
          <td>164.80</td>
          <td>165.05</td>
          <td>167.27</td>
          <td>26536944</td>
          <td>4.438942e+09</td>
          <td>116512</td>
          <td>7037498</td>
          <td>26.52</td>
          <td>May</td>
          <td>2017</td>
          <td>-0.052254</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>3</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-18</td>
          <td>165.05</td>
          <td>163.40</td>
          <td>164.40</td>
          <td>157.9</td>
          <td>158.25</td>
          <td>158.50</td>
          <td>161.06</td>
          <td>13905573</td>
          <td>2.239613e+09</td>
          <td>76746</td>
          <td>3245443</td>
          <td>23.34</td>
          <td>May</td>
          <td>2017</td>
          <td>-0.039685</td>
          <td>Slight or No change</td>
        </tr>
        <tr>
          <th>4</th>
          <td>PNB</td>
          <td>EQ</td>
          <td>2017-05-19</td>
          <td>158.50</td>
          <td>159.50</td>
          <td>162.25</td>
          <td>154.1</td>
          <td>155.20</td>
          <td>155.20</td>
          <td>157.59</td>
          <td>16311602</td>
          <td>2.570540e+09</td>
          <td>82394</td>
          <td>2816963</td>
          <td>17.27</td>
          <td>May</td>
          <td>2017</td>
          <td>-0.020820</td>
          <td>Slight or No change</td>
        </tr>
      </tbody>
    </table>
    </div>



Query 1.8
~~~~~~~~~

Find the average and median values of the column ‘Total Traded Quantity’
for each of the types of ‘Trend’. {Hint : use ‘groupby()’ on the ‘Trend’
column and then calculate the average and median values of the column
‘Total Traded Quantity’}

.. code:: ipython3

    print('Group wise Medians:')
    print(df.loc[:,['Trend', 'Total Traded Quantity']].groupby('Trend').agg(np.median))
    print('\n\nGroup wise Means:')
    print(df.loc[:,['Trend', 'Total Traded Quantity']].groupby('Trend').agg(np.mean))


.. parsed-literal::

    Group wise Medians:
                         Total Traded Quantity
    Trend                                     
    Slight or No change               18963362
    
    
    Group wise Means:
                         Total Traded Quantity
    Trend                                     
    Slight or No change           2.515651e+07


Query 1.9
~~~~~~~~~

SAVE the dataframe with the additional columns computed as a csv file
week2.csv. In Module 2, you are going to get familiar with matplotlib,
the python module which is used to visualize data.

.. code:: ipython3

    df.to_csv('week2.csv')

