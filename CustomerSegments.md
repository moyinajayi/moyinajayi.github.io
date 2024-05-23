## Customer Behaviour analysis and segementation using KMeans.

**Project description:**  This is a data analysis project that involves reading, cleaning, exploring, and performing advanced analyses on a retail dataset.
The project uses Kmeans Clustering algorithm for identifying .

This project covers data cleaning, exploratory data analysis (EDA), data visualization, and customer segmentation using machine learning techniques. 

### 1. Importing libraries and Loading the data

 I used a dataset named OnlineRetail.csv, which contains transactional data from an online retail store. The primary goal was to explore the dataset, clean it, visualize important patterns, and perform customer segmentation
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/1dd5cc1a-05f8-4f53-82ab-93ed3cef801a)\ ![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/ef198a92-0413-4d6f-9b09-b7abd3f70b30)


```javascript
if (isAwesome){
  return true
}
```

### 2. Data Visualization

After removing the nulll values from the dataset, I created two addditonal columsn 'Month' and 'Day of Week' based of tdh invoice date column. 
The goal was to further understand if there were any pointers to the actual day of week, or some other insights from the date
Below  are some visualizatiions showing trend and distributions.

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/12ea5d21-e2d4-4d01-9b60-3e779eadfd20)

The Barplots show that there were no transactions on saturday, and even though the highest transactions were in the 11th month, the total amount spent was highest in the first month in January

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/39f1f7ee-a0ab-4aa9-874f-a921c7b192af)


In addition this visuals show for teh top 5 countries and the tiop stock items purchased 
![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/fa2c6cc6-828c-4e81-a884-c5253ae4185c)



### 3.Analysis using Recency Frequency and Spend (RFS)

Recency, Frequency, Monetary model (RFM), is a behavior based analysis technique used to segment customers by examining their transaction history. Recency is calculated as the number of days since the last purchase
Recency is calculated, frequency is the number of transactions per customer, and Spend is the total amount spent per customer.

```python
last_transaction_date = df.groupby('CustomerID')['InvoiceDate'].max()
reference_date = max(df['InvoiceDate'])
days_difference = (reference_date - last_transaction_date).dt.days
days_difference = days_difference.reset_index().rename(columns={'InvoiceDate': 'recency'})
```
These 2 metrics are then merged into a single dataframe.

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/0edc2421-bd39-4d44-919c-a4229c163394)

And these are boxplots to show the Outliers in the RFS data distributions

![image](https://github.com/moyinajayi/moyinajayi.github.io/assets/9222400/a58e8814-c381-4661-8e36-f87844461b16)

The outliers were mostly in the Frequency and spend coluumns and were removed before applying Kmeans algorthm



### 4. Clustering customers using KMeans

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
