# **Starbucks-Customer-Segmentation**

# Business Undersatnding

**Starbucks Corporation** is a global coffee company with over 30,000 stores across 80+ countries. To build customer loyalty, it offers a **Starbucks Rewards Program**, where members receive promotional offers through various channels. However, customer responses to these offers vary significantly, leading to missed engagement opportunities and inefficient marketing. Understanding customer behavior is key to delivering relevant promotions and improving customer retention.

# Problem statement

Starbucks currently promotes products to customers **without any prior segmentation**, treating all users as a single group. This approach leads to inefficient marketing and lower engagement with promotional offers.
By analyzing customer behavior data, the company can discover **patterns and similarities** that help in grouping users with common characteristics. This enables **targeted marketing**, helping Starbucks maximize offer redemption and revenue, while reducing promotional costs by focusing on the most responsive customer segments.

# Project Objective

This project involves analyzing user demographics and offer interactions to identify **distinct customer segments**. These segments allow the company to gain behavioral insights and develop better marketing strategies tailored to specific groups.

Here’s a brief outline of what I did:
- Merged and cleaned dataset given in this repo.
- Transformed raw data through preprocessing.
- Applied K means clustering algorithum to group users.
- Interpreted clusters to derive business insights

# Dataset

The project uses three JSON files provided by Udacity that simulate real-world data from the Starbucks Rewards Program:

- **Portfolio.json**: Contains details of the promotional offers (type, duration, channels, difficulty, reward).
- **Profile.json**: Contains customer demographic data (age, gender, income, date of joining).
- **Transcript.json**: Contains event-based records of user interactions with offers and transactions (e.g., offer received, offer viewed, offer completed, transaction made).

Datasets are available in this repositry itself.

# Project workflow 

### 1. Data Understanding

Firstly, I explored the three datasets to understand their structure features, and how they connect with each other — especially how user behavior can be tracked across events and offer types.

### 2. Data Cleaning

Then, I cleaned the dataset by removing null values from the 'gender' and 'income' columns, filtered out invalid entries (like age = 118), and dropped customers with no meaningful activity. I also corrected inconsistent data types and renamed several columns for better clarity and understanding during analysis.

### 3. Exploratory Data Analysis (EDA)

Then, I performed comprehensive EDA on all datasets:

1. **Univariate Analysis**  
   - Analyzed each DataFrame individually  
   - Reviewed summary statistics for all variables related to offers, demographics, and event logs

2. **Bivariate Analysis**  
   - Explored relationships within customer demographic data (`profile`): age, gender, and income  
   - Identified trends that might influence offer response behavior

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

<img width="589" height="455" alt="image" src="https://github.com/user-attachments/assets/11ced1e0-9217-4052-b700-7650db11db24" />


### 7. Results & Visualizations

Once the model was trained, I analyzed the clusters using visualizations like bar charts,scatter plot and pair plots to understand the differences in behavior, spending, and responsiveness across segments.

Below are some visualizations and insights from my analysis:












