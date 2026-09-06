# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```python
import pandas as pd
data ={
    'Month': ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'June', 'July', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'],
    'Laptop': [15, 18, 20, 22, 25, 28, 30, 32, 35, 38, 40, 42],
    'Tablet': [10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32],
    'SmartPhone' : [5, 7, 9, 11, 13, 15, 17, 19, 21, 23, 25, 27],
    'Accessories' : [2, 4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24]
}
df=pd.DataFrame(data)
df
import matplotlib.pyplot as plt
plt.plot(df['Month'],df['Laptop'],color="red",linestyle="dashed")
plt.title("Monthly Sales of Laptops")
plt.xlabel("Month")
plt.ylabel("Units Sold")
plt.show()
plt.plot(df['Month'],df['Laptop'],marker='o',label='Laptop')
plt.plot(df['Month'],df['SmartPhone'],marker='o',label='SmartPhone')

plt.title("Monthly product sales")
plt.xlabel("Month")
plt.ylabel("Units Sold")
plt.legend()
plt.show()

pro_sales={
    'Laptop':df['Laptop'].sum(),
    'Tablet':df['Tablet'].sum(),
    'SmartPhone':df['SmartPhone'].sum(),
    'Accessories':df['Accessories'].sum()
}
product=list(pro_sales.keys())
sales=list(pro_sales.values())
colors=['skyblue','lightcoral','yellowgreen','lightpink']
plt.bar(product,sales,color=colors)
plt.title("Product Sales")
plt.xlabel("Product")
plt.ylabel("Total Units Sold")

plt.show()

plt.barh(product,sales,color=colors)
plt.title("Product Sales")
plt.ylabel("Product")
plt.xlabel("Total Units Sold")

plt.show()

plt.bar(df['Month'],df['Laptop'],label='Laptop')
plt.bar(df['Month'],df['Tablet'],bottom=df['Laptop'],label='Tablet')
plt.title("Monthly Product Sales")
plt.xlabel("Month")
plt.ylabel("Units Sold")
plt.legend()
plt.show()

plt.fill_between(df['Month'],df['Laptop'],color='skyblue',alpha=0.5)
plt.title("Laptop sales trend")
plt.xlabel("Month")
plt.ylabel("Units Sold")
plt.show()

plt.stackplot(df['Month'],df['Laptop'],df['Tablet'],df['SmartPhone'],df['Accessories'],labels=['Laptop','Tablet','SmartPhone','Accessories'])
plt.title("Product Sales Trend")
plt.xlabel("Month")
plt.ylabel("Units Sold")
plt.legend(loc='upper left')
plt.show()

order_sales = [
    10, 12, 15, 18, 20, 22, 25, 28,
    30, 32, 35, 35, 38, 40, 42, 45,
    48, 50, 52, 55, 60, 65, 70, 75,
    80, 85, 90, 100
]
plt.hist(order_sales,bins=4)
plt.title("Order Sales Distribution")
plt.xlabel("Order Sales")
plt.ylabel("Frequency")
plt.show()

plt.hist(df['Laptop'],bins=5)
plt.title("Laptop Sales Distribution")
plt.xlabel("Laptop Sales")
plt.ylabel("Frequency")
plt.show()

plt.hist(df['Laptop'],bins=5,alpha=0.5,label='Laptop')
plt.hist(df['Tablet'],bins=5,alpha=0.5,label='Tablet')
plt.hist(df['SmartPhone'],bins=5,alpha=0.5,label='SmartPhone')

plt.title("Product Sales Distribution")
plt.xlabel("Product Sales")
plt.ylabel("Frequency")
plt.legend()
plt.show()

plt.pie(sales,labels=product,autopct='%1.1f%%')
plt.title("Product Sales Distribution")
plt.show()

import pandas as pd
import matplotlib.pyplot as plt
data={
    'Product':['Laptop','Tablet','SmartPhone','Accessories'],
    'Sales':[280,300,100,200]
}
df1=pd.DataFrame(data)
explode=[0,0.1,0,0]
colors=['gold','skyblue','lightgreen','orange']
plt.pie(
    df1['Sales'],
    labels=df1['Product'],
    explode=explode,
    colors=colors,
    autopct='%1.1f%%',
    shadow=True,
    startangle=90,
    textprops={'fontsize':11},
    wedgeprops={'width':0.8}
)
plt.title("Product Sales Distribution")
plt.axis('equal')
plt.show()

labels='python','c','c++','java'
sizes=[215,130,245,210]
colors=['gold','skyblue','lightgreen','orange']
explode=(0,0.4,0,0.5)
plt.pie(sizes,explode=explode,labels=labels,colors=colors,autopct='%1.1f%%',shadow=True,startangle=90)
plt.axis('equal')
plt.show

data={
    'Product':['Laptop','Tablet','SmartPhone','Accessories'],
    'Sales':[120,150,180,200]
}
dfn=pd.DataFrame(data)
dfn

sales=[120,135,150,145,170,180,
       190,175,200,220,250,280,
       310,125,140,155,165,185]

plt.boxplot(sales)
plt.title("Sales Distribution")
plt.ylabel("Sales")

plt.show()

sales=[120,135,150,145,170,180,
       190,175,200,220,250,280,
       310,125,140,155,165,185,600]

plt.boxplot(sales)
plt.title("Sales Distribution with Outlier")
plt.ylabel("Sales")

plt.show()

laptop=[120,135,150,145,165,170,180,190,175,200]
mobile=[220,250,280,310,240,260,270,290,300,230]
tablet=[125,140,155,165,185,195,205,215,235,240]
plt.boxplot([laptop,mobile,tablet],labels=['Laptop','Mobile','Tablet'])
plt.title("Product Sales Distribution")
plt.xlabel("Product")
plt.ylabel("Units sold")

plt.show()

plt.boxplot([laptop,mobile,tablet],labels=['Laptop','Mobile','Tablet'],vert=False)
plt.title("Product Sales Distribution")

plt.xlabel("Units sold")

plt.show()

plt.boxplot(
    sales,
    showmeans=True
)
plt.title("Sales Distribution")
plt.ylabel("Sales")

plt.show()

plt.scatter(df['Laptop'],df['SmartPhone'])
for i in range(len(df)):
  plt.annotate(
      df['Month'][i],
      (df['Laptop'][i],df['SmartPhone'][i])
  )
plt.title('Laptop vs SmartPhone Sales')
plt.xlabel('Laptop Sales')
plt.ylabel('SmartPhone Sales')

plt.scatter(
    df['Month'],
    df['Laptop'],
    color='blue',
    s=100,label='Laptop'
)
plt.scatter(
    df['Month'],
    df['SmartPhone'],
    color='red',
    s=100,
    label='SmartPhone'
)
plt.title("Laptop vs SmartPhone Sales")
plt.xlabel("Month")
plt.ylabel("Sales")
plt.grid(True)
plt.legend()
plt.show()

```
## OUTPUT
<img width="530" height="548" alt="Screenshot 2026-08-27 222609" src="https://github.com/user-attachments/assets/bca22a1d-0c18-45ef-8b9c-fe2d05780c94" />

<img width="762" height="682" alt="Screenshot 2026-08-27 222621" src="https://github.com/user-attachments/assets/f9f940c1-8213-468a-a0e1-d63c44f82cf7" />

<img width="743" height="694" alt="Screenshot 2026-08-27 222632" src="https://github.com/user-attachments/assets/085ded1a-46e0-4cb2-bf5f-1085324eb153" />

<img width="628" height="481" alt="Screenshot 2026-08-27 222653" src="https://github.com/user-attachments/assets/da01a6f7-fa60-40fe-a80a-87bc696032a4" />

<img width="742" height="614" alt="Screenshot 2026-08-27 222659" src="https://github.com/user-attachments/assets/34d0990a-1b1d-4956-8364-eb4b5c80301b" />

<img width="669" height="701" alt="Screenshot 2026-08-27 222710" src="https://github.com/user-attachments/assets/7a30c276-4b29-45b2-a08f-2c9068d80e1e" />

<img width="691" height="655" alt="Screenshot 2026-08-27 222717" src="https://github.com/user-attachments/assets/17092a86-6786-4616-adac-115b6e53f576" />

<img width="1176" height="682" alt="Screenshot 2026-08-27 222725" src="https://github.com/user-attachments/assets/ec004240-1c62-46db-bede-12139337c4ef" />

<img width="709" height="607" alt="Screenshot 2026-08-27 222736" src="https://github.com/user-attachments/assets/705ac3c0-2160-4569-8461-edc344113a74" />

<img width="649" height="588" alt="Screenshot 2026-08-27 222743" src="https://github.com/user-attachments/assets/cc0051d1-a2dd-496e-b56d-94b9fe9f3e5a" />

<img width="685" height="665" alt="Screenshot 2026-08-27 222752" src="https://github.com/user-attachments/assets/5cd0c536-8534-47d0-b5c3-113e898da843" />

<img width="601" height="566" alt="Screenshot 2026-08-27 222800" src="https://github.com/user-attachments/assets/c9f80429-99e2-4399-ba7c-afebac869139" />

<img width="598" height="458" alt="Screenshot 2026-08-27 222814" src="https://github.com/user-attachments/assets/3b48234a-42c8-4f9b-b5a2-e787af3df6a6" />

<img width="739" height="411" alt="Screenshot 2026-08-27 222821" src="https://github.com/user-attachments/assets/61441b75-98be-451d-9ffc-58f75ad2e5ea" />

<img width="597" height="445" alt="Screenshot 2026-08-27 222829" src="https://github.com/user-attachments/assets/eb8d6101-06e0-42df-a52c-7f454d8472ff" />

<img width="649" height="456" alt="Screenshot 2026-08-27 222835" src="https://github.com/user-attachments/assets/af4e7e13-6f44-4a07-a44b-14c63770c224" />

<img width="652" height="469" alt="Screenshot 2026-08-27 222842" src="https://github.com/user-attachments/assets/7b2d888b-c004-4c98-8e51-b45bca3f3cf4" />

<img width="639" height="472" alt="Screenshot 2026-08-27 222850" src="https://github.com/user-attachments/assets/0592f9b8-382a-4018-b86e-551a8c6bfdf9" />

<img width="678" height="491" alt="Screenshot 2026-08-27 222857" src="https://github.com/user-attachments/assets/d16da082-0626-4bd6-8221-662377e17ea7" />

<img width="611" height="468" alt="Screenshot 2026-08-27 222903" src="https://github.com/user-attachments/assets/1ef51e27-bcfc-40a5-b390-3b82238cd9fe" />

<img width="633" height="479" alt="Screenshot 2026-08-27 222910" src="https://github.com/user-attachments/assets/1e945369-496b-4b65-b197-71974a220a4e" />




# Result:
 Thus, the Data Visualization using matplot python library for the given datas is successfully verified.

 # SUMMARY
 The given product sales dataset was successfully created and analyzed using the Pandas and Matplotlib libraries.
Various visualization techniques such as line charts, bar charts, stacked bars, area charts, histograms, pie charts, box plots, and scatter plots were applied.
These visualizations helped identify sales trends, product comparisons, data distributions, relationships, and outliers effectively.
Different plot parameters such as labels, legends, markers, grids, colors, annotations, and titles were used to improve readability.
Thus, the experiment successfully demonstrates how data visualization can convert raw data into meaningful graphical insights for better analysis and decision-making.
