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

#### Apriori Algorithm
- is an influential algorithm for mining frequent itemsets for boolean associations rules
- Uses prior knowledge of frequent itemset properties (Apriori)
- Uses  K frequent itemset to find K+1 itemsets
- Based on three concepts:
	- Frequent Itemset
	- Apriori property
	- Join Operations

![[IMG_20250304_014819229_HDR.jpg]]![[IMG_20250304_014839219_HDR.jpg]]![[IMG_20250304_014833766_HDR.jpg]]