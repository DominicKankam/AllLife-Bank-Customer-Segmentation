
### Context
AllLife Bank wants to focus on its credit card customer base in the next financial year. They have been advised by their marketing research team, that the penetration in the market can be improved. Based on this input, the Marketing team proposes to run personalized campaigns to target new customers as well as upsell to existing customers. Another insight from the market research was that the customers perceive the support services of the back poorly. Based on this, the Operations team wants to upgrade the service delivery model, to ensure that customer queries are resolved faster. 

### Objective
To identify different segments in the existing customer database based on their spending patterns as well as past interaction with the bank using clustering algorithms and provide recommendations to the bank on how to better market and service these customers.

### Data Description
The data provided is of various customers of a bank and their financial attributes like credit limit, the total number of credit cards the customer has, and different channels through which customers have contacted the bank for any queries (including visiting the bank, online and through a call center).

### Data Dictionary
Sl_No: Primary key of the records
Customer Key: Customer identification number
Average Credit Limit: Average credit limit of each customer for all credit cards
Total credit cards: Total number of credit cards possessed by the customer
Total visits bank: Total number of Visits that customer made (yearly) personally to the bank
Total visits online: Total number of visits or online logins made by the customer (yearly)
Total calls made: Total number of calls made by the customer to the bank or its customer service department (yearly)

### Importing necessary libraries
%load_ext nb_black
# this will help in making the Python code more structured automatically
​
# Libraries to help with reading and manipulating data
import numpy as np
import pandas as pd
​
# Libraries to help with data visualization
import matplotlib.pyplot as plt
import seaborn as sns
​
# Removes the limit for the number of displayed columns
pd.set_option("display.max_columns", None)
# Sets the limit for the number of displayed rows
pd.set_option("display.max_rows", 200)
​
# to scale the data using z-score
from sklearn.preprocessing import StandardScaler
​
# to perform k-means clustering and compute silhouette scores
from sklearn.cluster import KMeans
from sklearn.metrics import silhouette_score
​
# to visualize the elbow curve and silhouette scores
from yellowbrick.cluster import KElbowVisualizer, SilhouetteVisualizer
​
​
# to compute distances
from scipy.spatial.distance import cdist,pdist
​
# to perform hierarchical clustering, compute cophenetic correlation, and create dendrograms
from sklearn.cluster import AgglomerativeClustering
from scipy.cluster.hierarchy import dendrogram, linkage, cophenet
​
# to perform PCA
from sklearn.decomposition import PCA
The nb_black extension is already loaded. To reload it, use:
  %reload_ext nb_black
  
# loading the dataset
data = pd.read_excel("Credit Card Customer Data.xlsx")
data.shape
(660, 7)
Dataset has 660 rows and 7 columns
