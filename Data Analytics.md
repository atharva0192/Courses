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

### Apriori Algorithm
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