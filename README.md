# **STARBUCKS CUSTOMER SEGMENTATION**

# Business Undersatnding : 

- **Starbucks Corporation** is a global coffee company with over 30,000 stores across 80+ countries. To build customer loyalty, it offers a **Starbucks Rewards Program**, where members receive promotional offers through various channels. However, customer responses to these offers vary significantly, leading to missed engagement opportunities and inefficient marketing. Understanding customer behavior is key to delivering relevant promotions and improving customer retention.

# Problem statement : 

- Starbucks currently promotes products to customers **without any prior segmentation**, treating all users as a single group. This approach leads to inefficient marketing and lower engagement    with promotional offers. By analyzing customer behavior data, the company can discover **patterns and similarities** that help in grouping users with common characteristics. This enables        **targeted marketing**, helping Starbucks maximize offer redemption and revenue, while reducing promotional costs by focusing on the most responsive customer segments.

# Project Objective : 

- This project involves analyzing user demographics and offer interactions to identify **distinct customer segments**. These segments allow the company to gain behavioral insights and develop     better marketing strategies tailored to specific groups.

  Here’s a brief outline of what I did:
  - Merged and cleaned dataset given in this repo.
  - Transformed raw data through preprocessing.
  - Applied K means clustering algorithum to group users.
  - Interpreted clusters to derive business insights

# Dataset : 

The project uses three JSON files provided by Udacity that simulate real-world data from the Starbucks Rewards Program:

- **Portfolio.json**: Contains details of the promotional offers (type, duration, channels, difficulty, reward).
- **Profile.json**: Contains customer demographic data (age, gender, income, date of joining).
- **Transcript.json**: Contains event-based records of user interactions with offers and transactions (e.g., offer received, offer viewed, offer completed, transaction made).

Datasets are available in this repositry itself.

# Project workflow : 

### 1. Data Understanding

Firstly, I explored the three datasets to understand their structure features, and how they connect with each other — especially how user behavior can be tracked across events and offer types.

### 2. Data Cleaning

Then, I cleaned the dataset by removing null values from the 'gender' and 'income' columns, filtered out invalid entries (like age = 118), and dropped customers with no meaningful activity. I also corrected inconsistent data types and renamed several columns for better clarity and understanding during analysis.

### 3. Exploratory Data Analysis (EDA)

I then performed EDA on the all DataFrames individually to gain a comprehensive understanding of the data.
Univariate analysis was performed on each DataFrame, summarizing the statistics of all variables related to offers, customers, and events. Bivariate analysis was applied to the customer demographic data to explore the relationships between age, gender, and income.

### 4. Data Preprocessing

After that, I merged all three datasets into one customer-level view and created several new features, such as:
- Total offers received, viewed, and completed.
- Total amount spent according to tranactions.
- find out offer view and completion rate 

I also encoded categorical variables and scaled the data to make it ready for clustering.

### 5. Customer Segmentation

Then, I segmented customers based on their behavior during the campaign month. I extracted key features for each customer, including the number of offers received, viewed, and completed, as well as the number of transactions made and the total amount spent. Using these metrics, I grouped customers into meaningful segments to better understand engagement levels and spending patterns.

### 6. Model Training

I applied **K-Means Clustering** to segment customers based on demographic and behavioral features. To determine the ideal cluster count, I used both the **Elbow Method** and **Silhouette Score**. After selecting the optimal number of clusters, I trained the model and labeled each customer accordingly for further analysis.

<img width="589" height="455" alt="image" src="https://github.com/user-attachments/assets/11ced1e0-9217-4052-b700-7650db11db24" /> <img width="576" height="455" alt="image" src="https://github.com/user-attachments/assets/2c554cc6-d3e5-49d4-b126-85656553fa04" />

### 7. Results & Visualizations

Once the model was trained, I analyzed the clusters using visualizations like bar charts,scatter plot and pair plots to understand the differences in behavior, spending, and responsiveness across segments.

Below are some visualizations and insights from my analysis:

<img width="571" height="455" alt="image" src="https://github.com/user-attachments/assets/dad5f0ce-b8ea-43d2-800a-449167854135" />


<img width="2990" height="495" alt="image" src="https://github.com/user-attachments/assets/4295b3e6-82f8-47fe-be97-d1b7857e3767" />


<img width="2990" height="495" alt="image" src="https://github.com/user-attachments/assets/aa50acf9-def9-4703-bbe4-09c640f3d852" />


<img width="773" height="471" alt="image" src="https://github.com/user-attachments/assets/7b89fe5a-d155-42fe-9566-421cd37d04fd" />

### 8. Interpretation of Clusters

Finlly i interpreted the resulting customer segments according to their behaviour as follows:

<img width="409" height="411" alt="image" src="https://github.com/user-attachments/assets/5302b9c5-7836-4a26-8356-34d5ddea967d" />

<img width="1789" height="396" alt="image" src="https://github.com/user-attachments/assets/feaf66b2-acf9-446a-b7a1-82b9c0a10018" />


- **Most Valuable Customers (MVC) – Cluster 4** - High-spending users with excellent engagement and completion rates.
- **Regular Customers – Cluster 2** - Consistent, moderate spenders who engage steadily.
- **High Potential Customers – Cluster 0** - Users with strong responsiveness.
- **Offer Viewers Customers – Cluster 1** - Customers who frequently view promotions but seldom complete them.
- **Low Engagers Customers – Cluster 3** - Users with minimal interaction.













