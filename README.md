
# Customer Segmentation: RFM 
Customer segmentation and RFM analysis


Recency, frequency, and monetary value (RFM) analysis is a technique used in marketing to determine which customers are the most valuable. RFM is useful for estimating a company's revenue from both existing and potential customers by determining which customers are most likely to make repeat purchases of the company's items.

This package does the data processing for the inputted data, conducts RFM Analysis and provides ability to visualize the results and identify the most valueable customer segments. 

## Installation 

link to package: https://pypi.org/project/customersegmentationrfm/0.0.1/
### Dependencies

* Python (>=3.7)
* Pandas (>=1.2.4)
* NumPy (>=1.20.1)
* matplotlib (>=3.3.4)

------------------------------------
To install the package use:
```
pip install customersegmentationrfm==0.0.1

```


### Example Usage 

I used Online Retail Store data to illustrate functionality of the package. 
<br>
Here is the data I used for further analysis

<img width="950" alt="Screen Shot 2022-12-16 at 21 35 35" src="https://user-images.githubusercontent.com/103374702/208156103-d18e972d-4094-4403-9237-61dda6112fd0.png">

The package helps to investigate the data, find anomalies and understand its' overall structure and feauture distributions. 

```
rfm = CustomerSegmentation(df, customer_id='CustomerID', transaction_date='InvoiceDate', amount='Amount')
rfm.exploratory_analysis(df)
```
<img width="427" alt="Screen Shot 2022-12-16 at 21 51 39" src="https://user-images.githubusercontent.com/103374702/208158781-15f6ded7-32f8-4265-b1c9-25332575e2fe.png">

<img width="717" alt="Screen Shot 2022-12-16 at 21 40 42" src="https://user-images.githubusercontent.com/103374702/208156895-d08d225b-f1d0-4630-9e1a-cbceebe3f2be.png">
With the help of this function we can get descriptive statistics, and important information about the data, with which we are going to work. 

The package enables to find the RFM scores, segment the customers based on their scores. 

```
df_scores = rfm.produce_rfm_dateset(df)
df_scores.head()
```

<img width="357" alt="Screen Shot 2022-12-16 at 21 42 02" src="https://user-images.githubusercontent.com/103374702/208157136-f05636f7-5374-4f18-9d62-65679cdb4af2.png">

```
df_scores = rfm.calculate_rfm_score(df_values)
rfm_table = rfm.find_segments(df_scores)
segment_table = rfm.find_segment_df(rfm.rfm_table)
segment_table.head()
```

<img width="263" alt="Screen Shot 2022-12-16 at 21 44 51" src="https://user-images.githubusercontent.com/103374702/208157664-ea9cd6d2-b523-49d7-83cb-4e0e450c4aec.png">


We can also plot the distribution of segments, and visually identify the ones with highest number of customers

```
rfm.plot_segment_distribution()
```

<img width="661" alt="Screen Shot 2022-12-16 at 21 46 10" src="https://user-images.githubusercontent.com/103374702/208157860-7ed6a27d-c36a-4960-80eb-96849df7da73.png">


```
rfm.find_customers('Champions')
```

<img width="572" alt="Screen Shot 2022-12-16 at 21 47 20" src="https://user-images.githubusercontent.com/103374702/208158073-ce6912bc-5617-49a9-b2a7-b3db44293f29.png">
