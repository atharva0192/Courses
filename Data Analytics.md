
### Introduction 

#### Why Data Mining?
- **Data Explosion Problem**
	- Automated data collection tools and mature database technology leads to tremendous amounts of data stored in databases , data warehouses and other information repositories
	- We are drowning in data , but starving for knowledge
- Solution : Data Mining and Data warehousing
	- A **Data Warehouse** is a central repository where data from multiple sources is collected, stored, and managed for analysis and reporting. It is designed for **efficient querying and reporting** rather than real-time transaction processing
	- Data Mining is the process of discovering patterns, correlations, and useful insights from large datasets using machine learning, statistics, and artificial intelligence
		-  **Data Warehouses store the structured data** that data mining algorithms analyze.
		- **Data Mining extracts insights** that help organizations make data-driven decisions.
		- **Data Warehouses provide clean, consistent data**, making mining more effective.
- Applications 
	- Market Analysis and management
	- Risk analysis and management
	- Fraud Detection
	- Text Mining
	- Intelligent Query answering

#### **Applications of KDD (Knowledge Discovery in Databases)**

The **KDD process** is widely used across industries to extract valuable insights from large datasets. Below are key applications:


##### **1. Market Analysis and Management**

💡 **Use Case:** Understanding customer behavior, product trends, and optimizing marketing strategies.  
📌 **Techniques Used:** Association rule mining, clustering, classification.  
✅ **Examples:**

- **Customer Segmentation:** Grouping customers based on purchasing behavior (e.g., frequent shoppers vs. seasonal buyers).
- **Market Basket Analysis:** Discovering buying patterns (e.g., "People who buy diapers often buy baby wipes").
- **Churn Prediction:** Identifying customers likely to leave a service and taking preventive actions.



##### **2. Risk Analysis and Management**

💡 **Use Case:** Predicting risks in finance, insurance, and business operations.  
📌 **Techniques Used:** Regression analysis, anomaly detection, classification.  
✅ **Examples:**

- **Credit Risk Assessment:** Evaluating loan applicants to determine the likelihood of default.
- **Stock Market Prediction:** Analyzing historical data to identify profitable investment opportunities.
- **Supply Chain Risk Management:** Predicting supplier failures and optimizing inventory management.


##### **3. Fraud Detection**

💡 **Use Case:** Detecting fraudulent transactions in banking, e-commerce, and insurance.  
📌 **Techniques Used:** Anomaly detection, decision trees, neural networks.  
✅ **Examples:**

- **Credit Card Fraud Detection:** Identifying unusual transaction patterns that may indicate fraud.
- **Insurance Claim Fraud:** Detecting fake claims using pattern recognition and behavioral analysis.
- **Cybersecurity Threat Detection:** Spotting abnormal network traffic indicating possible cyberattacks.


##### **4. Text Mining**

💡 **Use Case:** Extracting meaningful information from unstructured text data.  
📌 **Techniques Used:** Natural Language Processing (NLP), sentiment analysis, topic modeling.  
✅ **Examples:**

- **Sentiment Analysis:** Understanding customer opinions from social media, reviews, or surveys.
- **Spam Detection:** Identifying spam emails using classification algorithms.
- **Automated Document Categorization:** Organizing large document collections into meaningful groups (e.g., news articles by topics).


##### **5. Intelligent Query Answering**

💡 **Use Case:** Enhancing database search with intelligent insights and context-aware answers.  
📌 **Techniques Used:** Information retrieval, semantic search, knowledge graphs.  
✅ **Examples:**

- **Chatbots & Virtual Assistants:** AI-powered assistants like ChatGPT, Siri, and Google Assistant providing smart responses.
- **Context-Aware Search Engines:** Improving search accuracy by understanding user intent (e.g., Google’s semantic search).
- **Healthcare Decision Support:** Answering medical queries based on a large database of medical literature.


#### KDD
- Knowledge Discovery in Database is the overall process of extraction useful knowledge from datasets.
##### Steps
- Step 1 : Learning the goals and knowledge of the application
- Step 2 : Data Selection 
- Step 3 : Data Cleaning and Data Preprocessing
- Step 4 : Data Reduction and Transformation
- Step 5 : Choosing Functions of Data Mining
- Step 6 : Choose the Mining Algorithm
- Step 7 : Pattern Evaluation and Presentation
- Step 8 : Use of discovered knowledge
![[Pasted image 20250305191432.png]]

##### Architecture of a Typical Data Mining System
![[Pasted image 20250305191542.png]]


#### **Types of Data Used in Data Mining**

Data Mining can be applied to various types of data, depending on the domain and the problem being solved. Here are the **main types of data used in Data Mining:**

---

##### **1. Structured Data**

📌 **Definition:** Data that is highly organized and stored in relational databases (tables with rows and columns).  
📌 **Examples:**

- Customer records (Name, Age, Address, Purchase history)
- Sales transactions (Product, Quantity, Price, Date)
- Financial data (Bank account details, transactions, credit scores)  
    📌 **Use Case:** Market analysis, fraud detection, risk management.

---

##### **2. Semi-Structured Data**

📌 **Definition:** Data that has some structure but is not strictly organized in tables.  
📌 **Examples:**

- JSON, XML files
- Emails (Subject, Sender, Content)
- Web pages (HTML with embedded metadata)  
    📌 **Use Case:** Web mining, email spam detection, recommendation systems.

---

##### **3. Unstructured Data**

📌 **Definition:** Data that has no predefined format, making it harder to analyze.  
📌 **Examples:**

- Text data (Emails, social media posts, blogs, reviews)
- Images and Videos (Medical scans, security footage, social media images)
- Audio data (Call center conversations, voice assistants)  
    📌 **Use Case:** Text mining, sentiment analysis, facial recognition, speech-to-text applications.

---

##### **4. Time-Series Data**

📌 **Definition:** Data collected over time at regular intervals.  
📌 **Examples:**

- Stock market prices
- Sensor data from IoT devices
- Weather data (Temperature, Humidity, Pressure)  
    📌 **Use Case:** Stock price prediction, anomaly detection in IoT, weather forecasting.

---

##### **5. Spatial Data (Geographical Data)**

📌 **Definition:** Data that represents the physical location or geographic information.  
📌 **Examples:**

- GPS tracking data (Google Maps, Uber)
- Satellite images
- Traffic data  
    📌 **Use Case:** Route optimization, land-use planning, disaster management.

---

##### **6. Graph Data**

📌 **Definition:** Data represented as a network of nodes and edges (relationships).  
📌 **Examples:**

- Social network connections (Facebook, LinkedIn)
- Fraud detection in financial transactions (Graphs of money transfers)
- Biological networks (Protein-protein interactions)  
    📌 **Use Case:** Social network analysis, fraud detection, bioinformatics.

---

##### **7. Streaming Data (Real-Time Data)**

📌 **Definition:** Data that is continuously generated and processed in real-time.  
📌 **Examples:**

- Live stock market transactions
- Website clickstream data
- IoT sensor readings  
    📌 **Use Case:** Real-time fraud detection, cybersecurity monitoring, autonomous vehicle control.



#### Data Mining Functionalities
##### **1. Descriptive Data Mining (Pattern Discovery)**

📌 **Definition:** Identifies patterns, associations, or clusters in data without making predictions.  
📌 **Types:**

###### **a) Association Rule Mining (Market Basket Analysis)**

- **Goal:** Find relationships between different items in a dataset.
- **Example:**
    - _If a customer buys bread and butter, they are likely to buy milk._
    - _Amazon recommends "Frequently Bought Together" items._
- **Technique Used:** Apriori Algorithm, FP-Growth.

---

###### **b) Clustering (Grouping Similar Data Points)**

- **Goal:** Group data into clusters based on similarity without predefined labels.
- **Example:**
    - _Customer segmentation in marketing (e.g., budget vs. premium customers)._
    - _Biological taxonomy: Grouping plants and animals based on characteristics._
- **Technique Used:** K-Means, DBSCAN, Hierarchical Clustering.

---

###### **c) Anomaly Detection (Outlier Detection)**

- **Goal:** Identify unusual patterns that do not conform to expected behavior.
- **Example:**
    - _Fraud detection in credit card transactions._
    - _Network intrusion detection in cybersecurity._
- **Technique Used:** Isolation Forest, One-Class SVM, LOF.

---

###### **d) Summarization (Data Abstraction)**

- **Goal:** Provide a compact representation of a dataset.
- **Example:**
    - _Generating reports that summarize customer behavior trends._
    - _Displaying key statistics (mean, median, mode) of sales data._
- **Technique Used:** Descriptive statistics, OLAP cubes.

---

##### **2. Predictive Data Mining**

📌 **Definition:** Uses historical data to predict future outcomes.  
📌 **Types:**

###### **a) Classification (Supervised Learning)**

- **Goal:** Assign new data points to predefined categories.
- **Example:**
    - _Email classification: Spam vs. Not Spam._
    - _Disease prediction: Predicting diabetes based on health data._
- **Technique Used:** Decision Trees, Random Forest, SVM, Neural Networks.

---

###### **b) Regression (Predicting Continuous Values)**

- **Goal:** Predict numerical outcomes based on input variables.
- **Example:**
    - _Predicting house prices based on size, location, and features._
    - _Forecasting stock market prices._
- **Technique Used:** Linear Regression, Ridge Regression, XGBoost.

---

###### **c) Time-Series Analysis (Forecasting)**

- **Goal:** Analyze data over time to make predictions.
- **Example:**
    - _Weather forecasting based on historical climate data._
    - _Sales forecasting for retail stores._
- **Technique Used:** ARIMA, LSTM, Prophet.

---

###### **d) Sequence Pattern Mining**

- **Goal:** Find patterns in sequential data.
- **Example:**
    - _Predicting the next word in a sentence (NLP applications like autocomplete)._
    - _Analyzing customer journey on e-commerce websites._
- **Technique Used:** PrefixSpan, GSP.


#### Multi-Dimensional View of Data Mining
##### **a) Data Dimension (Types of Data)**

📌 **What it refers to?**

- Data mining can be applied to different types of data.
- Data is structured in a **multi-dimensional model** (like OLAP cubes).

📌 **Examples:**

- **Transactional Data**: Sales records, online purchases.
- **Spatial Data**: Geographic locations, satellite images.
- **Text Data**: Social media posts, emails.
- **Time-Series Data**: Stock prices, weather reports.

---

##### **b) Knowledge Dimension (Types of Knowledge Discovered)**

📌 **What it refers to?**

- Different types of patterns extracted from data.

📌 **Examples:**

- **Association Rules**: "Customers who buy laptops often buy mouse pads."
- **Clusters**: Grouping customers based on purchase behavior.
- **Trends & Forecasts**: Predicting next month's sales based on past trends.
- **Anomalies**: Identifying unusual transactions for fraud detection.

---

##### **c) Technique Dimension (Methods Used)**

📌 **What it refers to?**

- The techniques used in data mining depend on the type of data and knowledge to be extracted.

📌 **Examples:**

- **Classification**: Decision Trees, Random Forest, Neural Networks.
- **Clustering**: K-Means, DBSCAN, Hierarchical Clustering.
- **Regression**: Linear Regression, XGBoost.
- **Sequence Pattern Mining**: PrefixSpan, GSP.

---

##### **d) Application Dimension (Industries & Use Cases)**

📌 **What it refers to?**

- The application of data mining across different domains.

📌 **Examples:**

- **Retail**: Customer segmentation, market basket analysis.
- **Finance**: Credit scoring, fraud detection.
- **Healthcare**: Disease prediction, drug discovery.
- **Cybersecurity**: Intrusion detection, anomaly detection.



### **What is Pre-processing in KDD?**

Knowledge Discovery in Databases (KDD) involves extracting meaningful patterns from large datasets. The first and most crucial step is **data pre-processing**, which ensures that the data is clean, integrated, transformed, and reduced before applying data mining techniques.

---

#### **1. Data Cleaning**

Data in real-world applications is often **incomplete, noisy, or inconsistent**. Data cleaning techniques handle missing values, outliers, and duplicate records.

### **Techniques for Data Cleaning:**

✅ **Handling Missing Data:**

- **Ignore missing values** (not recommended unless minimal impact).
- **Fill with a global constant** (e.g., “Unknown” or 0).
- **Fill with attribute mean/median/mode**.
- **Use regression or machine learning models** to predict missing values.

✅ **Removing Noisy Data (Outliers):**

- **Binning:** Sort data into bins and smooth noisy values.
- **Regression:** Fit a model to detect and correct noise.
- **Clustering:** Detect outliers as data points far from clusters.

✅ **Handling Inconsistent Data:**

- Detect inconsistencies using **integrity constraints** (e.g., date of birth should not be in the future).
- Use **data auditing tools** to correct errors.

---

#### **2. Data Integration**

Data may come from multiple sources (databases, spreadsheets, APIs). Data integration combines them into a **single unified dataset**.

#### **Challenges & Techniques:**

✅ **Schema Matching:** Align different databases by **matching column names and data types**.  
✅ **Entity Resolution:** Resolve different names for the same entity (e.g., "IBM" vs. "International Business Machines").  
✅ **Data Redundancy Handling:**
- Use **correlation analysis** to remove duplicate attributes.
- Normalize data to maintain consistency.

---

#### **3. Data Transformation**
Once integrated, data must be **transformed into a suitable format** for mining.
##### **Common Transformation Methods:**

✅ **Normalization (Feature Scaling)**:
- **Min-Max Scaling**: Rescales values between [0,1]
- **Z-score Standardization**: Transforms data with mean = 0 and std deviation = 1
- **Log Transformation**: Reduces skewness in data

✅ **Aggregation:**
- Convert raw data into summarized form (e.g., **daily → monthly sales data**).

✅ **Feature Construction:**
- Derive new attributes from existing ones (e.g., **age from date of birth**).

✅ **Encoding Categorical Data:**
- **One-Hot Encoding:** Converts categories into binary vectors.
- **Label Encoding:** Assigns unique numerical values to categories.

---

#### **4. Data Reduction**

Reducing the dataset size while preserving **important information** speeds up processing and improves efficiency.
#### **Techniques for Data Reduction:**
✅ **Dimensionality Reduction:**
- **Principal Component Analysis (PCA)**: Reduces features while preserving variance.
- **LDA (Linear Discriminant Analysis)**: Enhances class separability.

✅ **Feature Selection:**
- Remove **irrelevant or redundant** attributes using techniques like **Recursive Feature Elimination (RFE)**.

✅ **Data Sampling:**
- Reduce dataset size using **random sampling** or **stratified sampling** to maintain balance.

✅ **Data Compression:**
- Use **wavelet transforms** or **Huffman encoding** to compress data without losing information.

![[Pasted image 20250306094209.png]]
![[Pasted image 20250306094223.png]]


### Terms
- Frequent Itemset is an itemset whose support is greater than some user-specified minimum support
- Closed Frequent Itemset : An itemset is closed if none of its immediate supersets has the same support as that of the itemset
- Maximal Frequent Itemset: An itemset is maximal frequent if none of its immediate supersets is frequent

#### Downward closure of property of frequent patterns

##### All subsets of any frequent itemset is also frequent

If "Milk Bread butter" is frequent itemset then the following are also frequent:
- Milk
- butter
- bread
- Milk Bread
- Milk Butter
- Bread Butter

#### Need of Closed and Maximal Itemset
- Useful when huge amount of data is used in association rule mining
- If length of frequent set is **k** then by downward closure property all of its 2^k subset are also frequent
- Computationally expensive and no need to find the additional subsets and can be avoided using the frequent dataset with maximum length
- One disadvantage with maximal frequent itemset is that even all its subsets are frequent, we do not know their supports which is important for mining rules
- Closed Frequent Itemset is preferred.

![[Pasted image 20250303023550.png]]


#### Identify Frequent , Closed and Maximal Itemset
![[IMG_20250303_031441076_HDR.jpg]]![[IMG_20250303_031448433_HDR.jpg]]
![[Pasted image 20250303031809.png]]


### Apriori Algorithm

#### Terms
- Itemset : A collection of one or more Item
- Support Count(sigma) : It represents frequency of occurrence of itemset
- Support (s) : Fraction of transactions that contain an itemset
- Confidence(c): Measures how often Y appears in transaction containing X
#### Association Rule
- an implication expression of form X->Y where X and Y are itemsets.
- Support(X->Y) = P(XUY)
- Confidence(X->Y) = P(Y|X) = P(XUY) / P(X)

#### Algorithm
- is an influential algorithm for mining frequent itemsets for boolean associations rules
- Uses prior knowledge of frequent itemset properties (Apriori)
- Uses  K frequent itemset to find K+1 itemsets
- Based on three concepts:
	- Frequent Itemset
	- Apriori property
	- Join Operations
	
![[IMG_20250304_014819229_HDR.jpg]]![[IMG_20250304_014833766_HDR.jpg]]![[IMG_20250304_014839219_HDR.jpg]]

#### Advantages
- Easy to implement
- can be easily parallelized
- uses large item property

#### Disadvantages
- Requires many database scan
- Assumes transaction database is memory resident



### Improving the efficiency of Apriori Algorithm

#### Hash Based Techniques
- Hash table is used as dataset
- First Iteration to count support of each itemset
- From second iteration , efforts are made to enhance execution of Apriori Algorithm by utilizing hash table
- Minimizes the number of itemset generated in second iteration
- In second iteration we map the every combination into a diverse bucket and increment the bucket count
- if count is less than the min support then remove them from candidate sets
- Advantages - 
	- Reduce the number of scans
	- Remove the large candidates that cause the high input / output  cost
- In the given example total count of buckets less than the minimum count are removed and not considered for respective L
![[Pasted image 20250304030625.png]]		
![[Pasted image 20250304030554.png]]
	
#### Transaction Reduction
- Transaction that does not contain any frequent k-itemset cannot contain any frequent k+1 itemset.
- So such transaction is marked or removed from further consideration
- Remove the transactions in the row then the items in the column which are less than minimum support
- After removal remember to apply normal join operation to get the next candidate table
![[Pasted image 20250304031126.png]]

#### Partitioning 
- Any itemset that is frequent in the database must be frequent in at least one of the partitions of database
![[Pasted image 20250304031442.png]]![[Pasted image 20250304031947.png]]
#### Dynamic Itemset Counting
- It is an algorithm which reduces the number of passes made over the date while keeping the number of itemset which are counted in any pass relatively low
- This technique can add new candidate itemset at any marked start point the database during scanning of database
- Given example M = 2 means 2 partition of dataset
![[Pasted image 20250304032635.png]]
![[Pasted image 20250304032559.png]]
![[Pasted image 20250304032903.png]]
#### Sampling
- Basic Idea is to pick random sample S of the given data and then search for frequent itemset in S instead of D
- Possible to loss global frequent itemset. Can be reduced by lowering the min support
- Accuracy and efficiency tradeoff



### Frequent Pattern Growth Algorithm
- It is pattern growth approach for mining frequent itemset
- Divide and Conquer Strategy
- Step 1 : Compress in Frequent Pattern Tree which captures itemset association information
- Step 2: Set of conditional databases is formed from FP tree. Conditional Pattern base for each node represents various pattern fragment that we extract those which satisfy min confidence criteria
- So this approach reduces the size of the dataset to be searched and also given out various frequent pattern segments
#### Advantages
- Only 2 passes over dataset
- Compress the dataset
- No candidate generation
- Faster than Apriori
#### Disadvantages
- FP tree may not fit in the memory
- FP tree is expensive to build


### Multidimensional Association Rules

#### Single Dimensional or Intra Dimensional Association Rule
- Single Distinct Predict with its multiple occurrences
- I1  - > I2

#### Multidimensional or Inter Dimensional Association Rule
- Two or more predicate . Each occurs once
![[Pasted image 20250305173441.png]]
![[Pasted image 20250305173509.png]]
![[Pasted image 20250305173548.png]]
![[Pasted image 20250305173631.png]]
![[Pasted image 20250305173825.png]]

#### Hybrid Dimensional Association Rule
- Like multi dimensional but predicates are repeated
![[Pasted image 20250305173939.png]]



### Multilevel Association Rules

- When transaction data is taken for link analysis. It is present at the low level of abstraction
- Difficult to form association rules from it as data scarcity is there
- Using concept of hierarchies , transaction data can be represented at various levels of abstraction
- Here association rules are generated at multiple levels
- So instead of low level of abstraction , rules are generated from higher level of abstraction which represents common sense knowledge 

#### Concept Hierarchy 
- It is a sequence of mappings from a set of low level concepts to higher level , more general concepts
![[Pasted image 20250305174639.png]]

#### Need 
- Low level data has no significant pattern but useful information is hiding 
- Aim to find the hidden information in or between levels of abstraction
	- Uniform Support - uniform min support for all levels
	- Reduced Support - reduced min support for lower levels
	- Group Based Support - item or group based support 

#### Uniform Support
- Specifies the only one minimum support threshold for all levels
- Simple to implement
![[Pasted image 20250305175047.png]]
![[Pasted image 20250305175105.png]]
- At level 2 its not possible to get CASE 2 because the milk is ok different brand so there will be no association
- At level 1 this problem does not occur we get association 

##### Drawbacks
- if minimum support is too high it could miss some meaningful associations occurring at the low level 
- If set too low it will generate many unnecessary associations occurring at higher levels

#### Reduced Support
- Specifies different threshold at different levels
- Higher at higher level and lower at low levels

![[Pasted image 20250305175608.png]]
- So now we can extract the pattern at Level 2 (between brands of milk and bread) as well as at Level 1

#### Group based support
- Group wise threshold value for support and confidence is input by the user or expert
- Group is selected based on product price or item of interest. Because experts have insights as to which groups are more important than others
![[Pasted image 20250305175954.png]]




### Techniques for Mining MD
#### Static Discretization - Concept Heirarchy 
#### Quantitative Association rules - K Clusters
#### Distance based Association rules - Minimize the Interval Size
