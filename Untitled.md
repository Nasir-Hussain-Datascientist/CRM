```python
import pandas as pd

file_path='assignment.xlsx'
sheet_name='RetailStore Dataset '
df=pd.read_excel(file_path,sheet_name)

df.head(1)

```




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
      <th>Invoice ID</th>
      <th>Branch</th>
      <th>City</th>
      <th>Customer type</th>
      <th>Gender</th>
      <th>Product line</th>
      <th>Unit price</th>
      <th>Quantity</th>
      <th>Tax 5%</th>
      <th>Total</th>
      <th>Date</th>
      <th>Time</th>
      <th>Payment</th>
      <th>cogs</th>
      <th>gross margin percentage</th>
      <th>gross income</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>D750</td>
      <td>X</td>
      <td>Geelong</td>
      <td>Member</td>
      <td>Female</td>
      <td>Health and beauty</td>
      <td>75.19</td>
      <td>7</td>
      <td>26.3165</td>
      <td>552.4715</td>
      <td>2022-05-01 00:00:00</td>
      <td>13:08:00</td>
      <td>Ewallet</td>
      <td>526.155</td>
      <td>4.761905</td>
      <td>26.3165</td>
      <td>9.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 1000 entries, 0 to 999
    Data columns (total 17 columns):
     #   Column                   Non-Null Count  Dtype  
    ---  ------                   --------------  -----  
     0   Invoice ID               1000 non-null   object 
     1   Branch                   1000 non-null   object 
     2   City                     1000 non-null   object 
     3   Customer type            1000 non-null   object 
     4   Gender                   1000 non-null   object 
     5   Product line             1000 non-null   object 
     6   Unit price               1000 non-null   float64
     7   Quantity                 1000 non-null   int64  
     8   Tax 5%                   1000 non-null   float64
     9   Total                    1000 non-null   float64
     10  Date                     1000 non-null   object 
     11  Time                     1000 non-null   object 
     12  Payment                  1000 non-null   object 
     13  cogs                     1000 non-null   float64
     14  gross margin percentage  1000 non-null   float64
     15  gross income             1000 non-null   float64
     16  Rating                   1000 non-null   float64
    dtypes: float64(7), int64(1), object(9)
    memory usage: 132.9+ KB
    


```python
print(df.duplicated().sum())
```

    0
    


```python
print(df.describe(include='all'))
```

           Invoice ID Branch     City Customer type  Gender         Product line  \
    count        1000   1000     1000          1000    1000                 1000   
    unique        575      3        3             2       2                    6   
    top          D189      X  Geelong        Member  Female  Fashion accessories   
    freq            6    340      340           501     501                  178   
    mean          NaN    NaN      NaN           NaN     NaN                  NaN   
    std           NaN    NaN      NaN           NaN     NaN                  NaN   
    min           NaN    NaN      NaN           NaN     NaN                  NaN   
    25%           NaN    NaN      NaN           NaN     NaN                  NaN   
    50%           NaN    NaN      NaN           NaN     NaN                  NaN   
    75%           NaN    NaN      NaN           NaN     NaN                  NaN   
    max           NaN    NaN      NaN           NaN     NaN                  NaN   
    
             Unit price     Quantity       Tax 5%        Total  \
    count   1000.000000  1000.000000  1000.000000  1000.000000   
    unique          NaN          NaN          NaN          NaN   
    top             NaN          NaN          NaN          NaN   
    freq            NaN          NaN          NaN          NaN   
    mean      56.172130     5.510000    15.517119   325.721749   
    std       26.494628     2.923431    11.760502   246.918763   
    min       10.580000     1.000000     0.533500    11.178500   
    25%       33.375000     3.000000     6.022625   126.393875   
    50%       55.730000     5.000000    12.259500   257.262000   
    75%       78.435000     8.000000    22.669500   475.865750   
    max      100.460000    10.000000    49.900000  1047.650000   
    
                           Date      Time  Payment         cogs  \
    count                  1000      1000     1000  1000.000000   
    unique                   89       506        3          NaN   
    top     2022-07-02 00:00:00  19:48:00  Ewallet          NaN   
    freq                     20         7      345          NaN   
    mean                    NaN       NaN      NaN   310.204630   
    std                     NaN       NaN      NaN   235.158261   
    min                     NaN       NaN      NaN    10.645000   
    25%                     NaN       NaN      NaN   120.371250   
    50%                     NaN       NaN      NaN   245.002500   
    75%                     NaN       NaN      NaN   453.196250   
    max                     NaN       NaN      NaN   997.750000   
    
            gross margin percentage  gross income      Rating  
    count              1.000000e+03   1000.000000  1000.00000  
    unique                      NaN           NaN         NaN  
    top                         NaN           NaN         NaN  
    freq                        NaN           NaN         NaN  
    mean               4.761905e+00     15.517119     6.97270  
    std                6.131498e-14     11.760502     1.71858  
    min                4.761905e+00      0.533500     4.00000  
    25%                4.761905e+00      6.022625     5.50000  
    50%                4.761905e+00     12.259500     7.00000  
    75%                4.761905e+00     22.669500     8.50000  
    max                4.761905e+00     49.900000    10.00000  
    


```python
df=df.drop_duplicates()
```


```python
df.head(1)
```




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
      <th>Invoice ID</th>
      <th>Branch</th>
      <th>City</th>
      <th>Customer type</th>
      <th>Gender</th>
      <th>Product line</th>
      <th>Unit price</th>
      <th>Quantity</th>
      <th>Tax 5%</th>
      <th>Total</th>
      <th>Date</th>
      <th>Time</th>
      <th>Payment</th>
      <th>cogs</th>
      <th>gross margin percentage</th>
      <th>gross income</th>
      <th>Rating</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>D750</td>
      <td>X</td>
      <td>Geelong</td>
      <td>Member</td>
      <td>Female</td>
      <td>Health and beauty</td>
      <td>75.19</td>
      <td>7</td>
      <td>26.3165</td>
      <td>552.4715</td>
      <td>2022-05-01 00:00:00</td>
      <td>13:08:00</td>
      <td>Ewallet</td>
      <td>526.155</td>
      <td>4.761905</td>
      <td>26.3165</td>
      <td>9.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['Date']=pd.to_datetime(df['Date'])
df['Time']=pd.to_datetime(df['Time'],format='%H:%M:%S').dt.time

df['Profit']=df['gross income']-df['cogs']
```


```python
df.head(1)
```




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
      <th>Invoice ID</th>
      <th>Branch</th>
      <th>City</th>
      <th>Customer type</th>
      <th>Gender</th>
      <th>Product line</th>
      <th>Unit price</th>
      <th>Quantity</th>
      <th>Tax 5%</th>
      <th>Total</th>
      <th>Date</th>
      <th>Time</th>
      <th>Payment</th>
      <th>cogs</th>
      <th>gross margin percentage</th>
      <th>gross income</th>
      <th>Rating</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>D750</td>
      <td>X</td>
      <td>Geelong</td>
      <td>Member</td>
      <td>Female</td>
      <td>Health and beauty</td>
      <td>75.19</td>
      <td>7</td>
      <td>26.3165</td>
      <td>552.4715</td>
      <td>2022-05-01</td>
      <td>13:08:00</td>
      <td>Ewallet</td>
      <td>526.155</td>
      <td>4.761905</td>
      <td>26.3165</td>
      <td>9.1</td>
      <td>-499.8385</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["Gross Profit"]=(df['gross margin percentage']/100)*df['Total']
```


```python
import matplotlib.pyplot as plt
import pandas as pd

# Ensure 'Date' is in datetime format
df['Date'] = pd.to_datetime(df['Date'])

# Filter data for the year 2022
df_2022 = df[df['Date'].dt.year == 2022]

# Extract month from the 'Date' column
df_2022['Month'] = df_2022['Date'].dt.to_period('M')

# Aggregate total sales by month and branch
monthly_sales = df_2022.groupby(['Month', 'Branch'])['Total'].sum().unstack()

# Plot
plt.figure(figsize=(14, 7))

for branch in monthly_sales.columns:
    plt.plot(monthly_sales.index.astype(str), monthly_sales[branch], label=f'Branch {branch}')

# Add titles and labels
plt.title('Total Sales by Branch for the Year 2022')
plt.xlabel('Month')
plt.ylabel('Total Sales ($)')
plt.legend(title='Branch')
plt.grid(True)
plt.xticks(rotation=45)  # Rotate x-axis labels for better readability

# Save and show the plot
plt.savefig('sales_by_branch_2022.png')
plt.show()


```


    
![png](output_9_0.png)
    



```python
import pandas as pd

# Ensure 'Date' is in datetime format
df['Date'] = pd.to_datetime(df['Date'])

# Filter data for the year 2022
df_2022 = df[df['Date'].dt.year == 2022]

# Extract month from the 'Date' column
df_2022['Month'] = df_2022['Date'].dt.to_period('M').astype(str)  # Convert to string for better readability

# Aggregate total sales by month and branch
monthly_sales = df_2022.groupby(['Month', 'Branch'])['Total'].sum().reset_index()

# Rename columns for clarity
monthly_sales.columns = ['Month', 'Branch', 'Total Sales']

# Print the summary DataFrame
print("Monthly Sales Summary for Each Branch in 2022:")
print(monthly_sales)

# Optional: Save the DataFrame to a CSV file

```

    Monthly Sales Summary for Each Branch in 2022:
          Month Branch  Total Sales
    0   2022-01      X   29615.1395
    1   2022-01      Y   26740.7700
    2   2022-01      Z   30929.1575
    3   2022-02      X   18508.7500
    4   2022-02      Y   25693.4530
    5   2022-02      Z   19503.5400
    6   2022-03      X   27112.4370
    7   2022-03      Y   20968.7795
    8   2022-03      Z   25295.0335
    9   2022-04      X    4622.4405
    10  2022-04      Y    1763.4480
    11  2022-04      Z    1650.2360
    12  2022-05      X    3034.1205
    13  2022-05      Y    5061.4065
    14  2022-05      Z    4809.1645
    15  2022-06      X    2797.4875
    16  2022-06      Y    4166.7305
    17  2022-06      Z    2742.0070
    18  2022-07      X    3573.2510
    19  2022-07      Y    4399.1280
    20  2022-07      Z    3637.3340
    21  2022-08      X    3997.0815
    22  2022-08      Y    4092.9585
    23  2022-08      Z    5526.2370
    24  2022-09      X    3612.6050
    25  2022-09      Y    4253.1285
    26  2022-09      Z    6014.5515
    27  2022-10      X    3265.3595
    28  2022-10      Y    2403.2185
    29  2022-10      Z    4284.6235
    30  2022-11      X    4055.0855
    31  2022-11      Y    2349.2625
    32  2022-11      Z    3291.0195
    33  2022-12      X    2936.1130
    34  2022-12      Y    5215.3885
    35  2022-12      Z    3801.3025
    


```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Sample data loading
# df = pd.read_excel('your_data.xlsx', sheet_name='RetailStore Dataset')

# Ensure 'Date' is in datetime format
df['Date'] = pd.to_datetime(df['Date'])

# Extract month from the 'Date' column
df['Month'] = df['Date'].dt.to_period('M')

# Group by month, branch, and product line, then calculate total sales
monthly_product_sales = df.groupby(['Month', 'Branch', 'Product line'])['Total'].sum().reset_index()

# Find the top-selling product for each branch and month
top_products = monthly_product_sales.loc[monthly_product_sales.groupby(['Month', 'Branch'])['Total'].idxmax()]

# Plotting
plt.figure(figsize=(14, 7))
sns.barplot(data=top_products, x='Month', y='Total', hue='Product line', dodge=True)

# Add titles and labels
plt.title('Top-Selling Product by Branch and Month')
plt.xlabel('Month')
plt.ylabel('Total Sales ($)')
plt.legend(title='Product Line')
plt.xticks(rotation=45)  # Rotate x-axis labels for better readability
plt.grid(True)

# Save and show the plot
plt.savefig('top_selling_products_by_branch_month.png')
plt.show()

```


    
![png](output_11_0.png)
    



```python
import pandas as pd

# Assuming 'top_products' DataFrame is already available from the previous code

# Print the complete DataFrame for top-selling products
print("Top-Selling Products by Branch and Month:")
print(top_products)

# Print the summary statistics for total sales
print("\nSummary Statistics for Total Sales:")
print(top_products['Total'].describe())

# Print the total number of records
print("\nTotal Number of Records:")
print(top_products.shape[0])

# Print the number of unique months, branches, and product lines
print("\nUnique Counts:")
print(f"Months: {top_products['Month'].nunique()}")
print(f"Branches: {top_products['Branch'].nunique()}")
print(f"Product Lines: {top_products['Product line'].nunique()}")

# Print the total sales by branch
print("\nTotal Sales by Branch:")
print(top_products.groupby('Branch')['Total'].sum())

# Print the total sales by product line
print("\nTotal Sales by Product Line:")
print(top_products.groupby('Product line')['Total'].sum())

```

    Top-Selling Products by Branch and Month:
           Month Branch            Product line      Total
    4    2022-01      X      Home and lifestyle  7135.4355
    6    2022-01      Y  Electronic accessories  5796.4805
    14   2022-01      Z      Food and beverages  6113.9840
    20   2022-02      X      Food and beverages  5570.9675
    24   2022-02      Y  Electronic accessories  5307.4740
    31   2022-02      Z     Fashion accessories  4250.3115
    40   2022-03      X      Home and lifestyle  5809.9775
    45   2022-03      Y       Health and beauty  6058.7055
    48   2022-03      Z  Electronic accessories  6539.7900
    57   2022-04      X       Health and beauty  1557.3280
    63   2022-04      Y      Home and lifestyle   738.5760
    66   2022-04      Z      Food and beverages   833.0800
    69   2022-05      X  Electronic accessories   986.5635
    77   2022-05      Y       Health and beauty  1726.7505
    82   2022-05      Z       Health and beauty  2103.0315
    90   2022-06      X       Sports and travel  1044.3090
    94   2022-06      Y       Health and beauty  1041.8915
    98   2022-06      Z      Food and beverages  1419.6450
    104  2022-07      X      Home and lifestyle  1218.5000
    106  2022-07      Y  Electronic accessories  1621.9650
    110  2022-07      Z  Electronic accessories  1124.1890
    117  2022-08      X     Fashion accessories  1392.2675
    123  2022-08      Y       Sports and travel  1587.5200
    125  2022-08      Z     Fashion accessories  2128.1390
    130  2022-09      X     Fashion accessories  1026.0710
    135  2022-09      Y     Fashion accessories  1365.9675
    139  2022-09      Z     Fashion accessories  1275.0490
    148  2022-10      X      Home and lifestyle  1267.1890
    154  2022-10      Y       Sports and travel   856.0800
    155  2022-10      Z  Electronic accessories  1220.5125
    164  2022-11      X      Home and lifestyle  1552.7360
    167  2022-11      Y      Food and beverages   815.6000
    172  2022-11      Z      Food and beverages  1513.0105
    176  2022-12      X  Electronic accessories  1185.0225
    181  2022-12      Y     Fashion accessories  1680.0330
    187  2022-12      Z      Food and beverages  1725.4860
    
    Summary Statistics for Total Sales:
    count      36.000000
    mean     2460.823292
    std      2041.965713
    min       738.576000
    25%      1169.814125
    50%      1532.873250
    75%      2658.682125
    max      7135.435500
    Name: Total, dtype: float64
    
    Total Number of Records:
    36
    
    Unique Counts:
    Months: 12
    Branches: 3
    Product Lines: 6
    
    Total Sales by Branch:
    Branch
    X    29746.3670
    Y    28597.0435
    Z    30246.2280
    Name: Total, dtype: float64
    
    Total Sales by Product Line:
    Product line
    Electronic accessories    23781.9970
    Fashion accessories       13117.8385
    Food and beverages        17991.7730
    Health and beauty         12487.7070
    Home and lifestyle        17722.4140
    Sports and travel          3487.9090
    Name: Total, dtype: float64
    


```python
import pandas as pd
import matplotlib.pyplot as plt

# Group by month and branch, then calculate total sales
monthly_sales = df.groupby(['Month', 'Branch'])['Total'].sum().unstack()

# Plotting
plt.figure(figsize=(14, 7))
monthly_sales.plot(kind='bar', stacked=True, colormap='tab20')
plt.title('Monthly Sales Comparison Across Branches')
plt.xlabel('Month')
plt.ylabel('Total Sales ($)')
plt.xticks(rotation=45)
plt.legend(title='Branch')

# Save and show the plot
plt.savefig('monthly_sales_comparison_across_branches.png')
plt.show()

# Print descriptive data
print("Monthly Sales Comparison Across Branches:")
print(monthly_sales)

```


    <Figure size 1400x700 with 0 Axes>



    
![png](output_13_1.png)
    


    Monthly Sales Comparison Across Branches:
    Branch            X           Y           Z
    Month                                      
    2022-01  29615.1395  26740.7700  30929.1575
    2022-02  18508.7500  25693.4530  19503.5400
    2022-03  27112.4370  20968.7795  25295.0335
    2022-04   4622.4405   1763.4480   1650.2360
    2022-05   3034.1205   5061.4065   4809.1645
    2022-06   2797.4875   4166.7305   2742.0070
    2022-07   3573.2510   4399.1280   3637.3340
    2022-08   3997.0815   4092.9585   5526.2370
    2022-09   3612.6050   4253.1285   6014.5515
    2022-10   3265.3595   2403.2185   4284.6235
    2022-11   4055.0855   2349.2625   3291.0195
    2022-12   2936.1130   5215.3885   3801.3025
    


```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Pivot table for heatmap
pivot_table = df.pivot_table(values='Total', index='Month', columns='Product line', aggfunc='sum')

# Plotting
plt.figure(figsize=(14, 7))
sns.heatmap(pivot_table, annot=True, fmt='.2f', cmap='YlGnBu', linewidths=.5)
plt.title('Sales Performance by Product Line and Month')
plt.xlabel('Product Line')
plt.ylabel('Month')

# Save and show the plot
plt.savefig('sales_performance_by_product_line_and_month.png')
plt.show()

# Print descriptive data
print("Sales Performance by Product Line and Month:")
print(pivot_table)

```


    
![png](output_14_0.png)
    


    Sales Performance by Product Line and Month:
    Product line  Electronic accessories  Fashion accessories  Food and beverages  \
    Month                                                                           
    2022-01                   14575.5820           13451.7855          14899.4275   
    2022-02                   13184.8005           11989.7475          11932.6150   
    2022-03                   13490.1960            9883.1745          11970.9545   
    2022-04                    1745.7685            1116.2840           1320.3385   
    2022-05                     986.5635            1233.3310           1918.0500   
    2022-06                     925.9800            1239.4095           2290.4625   
    2022-07                    3105.4860            2352.2050           1815.2890   
    2022-08                     650.4125            4246.0175           2753.5260   
    2022-09                    2038.1715            3667.0875           1926.7325   
    2022-10                    1705.7165            2183.2995           1115.7215   
    2022-11                     183.5725            1151.5485           2952.2410   
    2022-12                    2230.7820            2243.0050           1725.4860   
    
    Product line  Health and beauty  Home and lifestyle  Sports and travel  
    Month                                                                   
    2022-01              13186.2855          14808.8025         16363.1840  
    2022-02               9521.0675           6848.5520         10228.9605  
    2022-03              10885.8895          14077.8430         13068.1925  
    2022-04               1692.7105           1690.5360           470.4870  
    2022-05               4382.2535           2759.2235          1625.2700  
    2022-06               1654.0760           1838.3065          1757.9905  
    2022-07               1532.0625           2092.6295           712.0410  
    2022-08               1086.1805           2085.8685          2794.2720  
    2022-09               1662.9570           1345.2000          3240.1365  
    2022-10               1013.9080           1884.6930          2049.8630  
    2022-11               1657.3775           2340.1645          1410.4635  
    2022-12               1345.9710           2545.5940          1861.9660  
    


```python
import pandas as pd
import matplotlib.pyplot as plt

# Find the top-selling product for each branch
top_selling_products = df.groupby(['Branch', 'Product line'])['Total'].sum().reset_index()
top_selling_products = top_selling_products.loc[top_selling_products.groupby('Branch')['Total'].idxmax()]

# Plotting
plt.figure(figsize=(14, 7))
sns.barplot(data=top_selling_products, x='Branch', y='Total', hue='Product line')

plt.title('Top-Selling Products in Each Branch')
plt.xlabel('Branch')
plt.ylabel('Total Sales ($)')
plt.legend(title='Product Line')

# Save and show the plot
plt.savefig('top_selling_products_in_each_branch.png')
plt.show()

```


    
![png](output_15_0.png)
    



```python
import pandas as pd
import matplotlib.pyplot as plt

# Sample data loading
# df = pd.read_excel('your_data.xlsx', sheet_name='RetailStore Dataset')

# Ensure 'Date' is in datetime format
df['Date'] = pd.to_datetime(df['Date'])

# Extract day of the week from the 'Date' column
df['DayOfWeek'] = df['Date'].dt.day_name()

# Calculate total sales for each day of the week for each branch
daily_sales_per_branch = df.groupby(['Branch', 'DayOfWeek'])['Total'].sum().reset_index()

# Sort days of the week to ensure the chart is in chronological order
days_order = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
daily_sales_per_branch['DayOfWeek'] = pd.Categorical(daily_sales_per_branch['DayOfWeek'], categories=days_order, ordered=True)
daily_sales_per_branch = daily_sales_per_branch.sort_values(['Branch', 'DayOfWeek'])

# Generate and save pie charts for each branch
branches = daily_sales_per_branch['Branch'].unique()
for branch in branches:
    branch_data = daily_sales_per_branch[daily_sales_per_branch['Branch'] == branch]
    
    plt.figure(figsize=(8, 8))
    plt.pie(branch_data['Total'], labels=branch_data['DayOfWeek'], autopct='%1.1f%%', startangle=140, colors=plt.get_cmap('Pastel1').colors)
    
    plt.title(f'Sales Distribution by Day of the Week for Branch {branch}')
    
    # Save and show the plot
    plt.savefig(f'sales_distribution_by_day_{branch}.png')
    plt.show()

    # Print descriptive data for each branch
    print(f"Sales Distribution by Day of the Week for Branch {branch}:")
    print(branch_data)

    # Print summary statistics for sales by day of the week for each branch
    print("\nSummary Statistics for Sales by Day of the Week:")
    print(branch_data['Total'].describe())

    # Print the total number of records
    print("\nTotal Number of Records:")
    print(branch_data.shape[0])

    # Print the total sales by day of the week for each branch
    print("\nTotal Sales by Day of the Week:")
    print(branch_data.set_index('DayOfWeek')['Total'])
    print("\n" + "-"*40 + "\n")

```


    
![png](output_16_0.png)
    


    Sales Distribution by Day of the Week for Branch X:
      Branch  DayOfWeek       Total
    1      X     Monday  14819.3745
    5      X    Tuesday  12693.3250
    6      X  Wednesday  15696.9870
    4      X   Thursday  15011.3210
    0      X     Friday  10564.7520
    2      X   Saturday  19698.2040
    3      X     Sunday  18645.9070
    
    Summary Statistics for Sales by Day of the Week:
    count        7.000000
    mean     15304.267214
    std       3168.291546
    min      10564.752000
    25%      13756.349750
    50%      15011.321000
    75%      17171.447000
    max      19698.204000
    Name: Total, dtype: float64
    
    Total Number of Records:
    7
    
    Total Sales by Day of the Week:
    DayOfWeek
    Monday       14819.3745
    Tuesday      12693.3250
    Wednesday    15696.9870
    Thursday     15011.3210
    Friday       10564.7520
    Saturday     19698.2040
    Sunday       18645.9070
    Name: Total, dtype: float64
    
    ----------------------------------------
    
    


    
![png](output_16_2.png)
    


    Sales Distribution by Day of the Week for Branch Y:
       Branch  DayOfWeek       Total
    8       Y     Monday  14989.7805
    12      Y    Tuesday  18766.3025
    13      Y  Wednesday  14982.2800
    11      Y   Thursday  15079.5055
    7       Y     Friday  14321.5510
    9       Y   Saturday  18930.2345
    10      Y     Sunday  10038.0180
    
    Summary Statistics for Sales by Day of the Week:
    count        7.000000
    mean     15301.096000
    std       3002.373065
    min      10038.018000
    25%      14651.915500
    50%      14989.780500
    75%      16922.904000
    max      18930.234500
    Name: Total, dtype: float64
    
    Total Number of Records:
    7
    
    Total Sales by Day of the Week:
    DayOfWeek
    Monday       14989.7805
    Tuesday      18766.3025
    Wednesday    14982.2800
    Thursday     15079.5055
    Friday       14321.5510
    Saturday     18930.2345
    Sunday       10038.0180
    Name: Total, dtype: float64
    
    ----------------------------------------
    
    


    
![png](output_16_4.png)
    


    Sales Distribution by Day of the Week for Branch Z:
       Branch  DayOfWeek       Total
    15      Z     Monday  15732.5045
    19      Z    Tuesday  13277.7440
    20      Z  Wednesday  16548.0220
    18      Z   Thursday  20058.2690
    14      Z     Friday  10465.6025
    16      Z   Saturday  16451.2805
    17      Z     Sunday  18950.7840
    
    Summary Statistics for Sales by Day of the Week:
    count        7.000000
    mean     15926.315214
    std       3259.714630
    min      10465.602500
    25%      14505.124250
    50%      16451.280500
    75%      17749.403000
    max      20058.269000
    Name: Total, dtype: float64
    
    Total Number of Records:
    7
    
    Total Sales by Day of the Week:
    DayOfWeek
    Monday       15732.5045
    Tuesday      13277.7440
    Wednesday    16548.0220
    Thursday     20058.2690
    Friday       10465.6025
    Saturday     16451.2805
    Sunday       18950.7840
    Name: Total, dtype: float64
    
    ----------------------------------------
    
    


```python
import seaborn as sns
import matplotlib.pyplot as plt

# Create a pivot table for the heatmap
pivot_table = df.pivot_table(index='Branch', columns='Customer type', values='Total', aggfunc='sum', fill_value=0)

# Plot the heatmap
plt.figure(figsize=(10, 6))
heatmap = sns.heatmap(pivot_table, annot=True, cmap='YlGnBu', fmt='g', linewidths=0.5)
plt.title('Heatmap of Total Sales by Customer Type and Branch')
plt.xlabel('Customer Type')
plt.ylabel('Branch')
plt.savefig('customertype.png')

# Print summary statistics
print("Heatmap Summary:")
for branch in pivot_table.index:
    print(f"Branch {branch}:")
    for customer_type in pivot_table.columns:
        value = pivot_table.loc[branch, customer_type]
        print(f"  Total Sales from {customer_type} customers: ${value}")

plt.show()

```

    Heatmap Summary:
    Branch X:
      Total Sales from Member customers: $54119.4755
      Total Sales from Normal customers: $53010.395
    Branch Y:
      Total Sales from Member customers: $54166.686
      Total Sales from Normal customers: $52940.986
    Branch Z:
      Total Sales from Member customers: $57329.7825
      Total Sales from Normal customers: $54154.424
    


    
![png](output_17_1.png)
    



```python

```
