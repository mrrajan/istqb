## Test Techniques 
Test techniques helps the tester to,
- define what to test in test analysis
- define how to test in test design
- develop a small and sufficient set of test cases in a systematic way
- define test conditions and identify coverage items

Three techniques,
**Blackbox technique:** 
- Also known as specification based technique. 
- The behavior of an application is examined/tested, without considering the internal structure or how the product is build. 
- Even if the implementation of the product changes for a requirements, the test cases are still valid.

**Whitebox technique:** 
- Also known as structure based technique.  
- The behavior of application evaluated/examined/tested by considering how the product is structured and the objects processing.
- The test case would be impacted when the implementation of the product is changed

**Experienced based technique:** 
- Effectiveness of the method totally depends on the experience and knowledge of the tester. 
- It is complementary to Black and White box techniques and it can explore the bugs not discovered by Black or white box technique. 
- The test cases are designed solely with the experience of the tester.


### Blackbox technique:
Commonly used techniques are,

**Equivalence Partitioning:** 
- Divides data into partitions based on the expectation that all the elements on the given partition would processed in the same way by the test object
- Theory behind this technique, If one value on a partition cause failure, then all other elements on the partition would also cause failure. Therefore one test for each partition is sufficient.
- Partition with valid values called as Valid partition, invalid values called as invalid partition.
- For 100% test coverage, The test should be performed with all partitions (Valid and Invalid) at least once.
- The partitions may be continuous or discrete, ordered or unordered, finite or infinite. The partitions must not overlap and must be non-empty sets
- In some cases, the test object may have multiple set of partitions (more than one input), in such cases the test case will coverage partition from different set of partitions. Simple coverage criterion in each case of multiple sets of partition is known as Each Choice Coverage

Example, A field accepts dates between January 1, 2000, and December 31, 2020. 
 - The valid partition values are, any date between Jan 1, 2000 to Dec 31,2020
 - The Invalid partition values are, any date before Jan 1, 2000 and any date after Dec 31, 2020.
The EP method should contain the value before Jan 1, 2000, in between Jan, 1 2000 to Dec 31, 2020 and After Dec 31, 2020.
 - So the value are, December 31, 1999 (Invalid: before the range), January 1, 2000 (Valid: start of range), June 15, 2010 (Valid: middle of range), December 31, 2020 (Valid: end of range), January 1, 2021 (Invalid: after the range). 
- **_Coverage:_** Number of partitions exercised by each test case at least once divided by total number of partitions.
- For the above case, we have total of three partitions,
    - Invalid partition above given range
    - Invalid partition below given range and 
    - Valid partition within given range. 
- Considering this, we have covered all the partitions in the each test at least once. So our coverage is 100%. 
- If we excluded any of the partition validation for example January 1, 2021, this would decrease the no of partitions covered as 2 and total partition is still 3. So the coverage would be 2/3*100 = 66.66%

In EP we should consider Before range, Start of the range, mid of the range, end of the range, After the range. And selecting the closest values to the ranges also suggested. For example, Both Jan 1, 2021 and Dec 31, 2021 are suitable for After range values, it is best to select the closest value to the range which Jan 1, 2021.

If we are asked to select only the valid EP values then we should have values from Start of the Range, End of the Range and Mid of the Range

**Boundary Value Analysis:**
- This can be performed only on Ordered Partitions
- The minimum and maximum values of the partitions are the boundary values
- If two elements belong to same partition, then elements between these are belong to the same partition.
- Two versions: 2-value BVA and 3-value BVA

**_2-Value BVA_**: Considers two values for a boundary,
1. Boundary itself
2. Values above or below the Boundary (Based on scenario)

Example, Consider a field accepts values from 1 to 10000. The boundary values are 1 and 10000. So we have boundaries and we have to select the adjacent which is lesser or greater than boundary.
The test case would be to test the fields with values 
 - 0 (below the boundary) (invalid partition)
 - 1 (boundary) (valid partition)
 - 10000 (boundary) (valid partition)
 - 10001 (above the boundary) (invalid partition)
**_Coverage:_** Defined as the No of boundary values tested divided by no of boundary values identified
- For the above case, we have 6 boundaries identified 0,1,2,9999,10000 and 10001
- But testing was exercised only for 4 values 0,1,10000 and 10001. So the coverage is 4/6*100=66.67%

**_3-Value BVA_**: Considers three values for a boundary,
1. Boundary itself
2. Value below the boundary
3. Value above the boundary

For the example above the 3 value BVA test cases would be,
 - 0 (below the boundary) (invalid partition)
 - 1 (boundary) (valid partition)
 - 2 (above the boundary) (valid partition)
 - 9999 (below the boundary) (valid partition)
 - 10000 (boundary) (valid partition)
 - 10001 (above the boundary) (invalid partition)
**_Coverage:_** Defined as the No of boundary values and its neighbors tested divided by no of boundary values and neighbors identified
- For the above case, we have 6 boundaries identified 0,1,2,9999,10000 and 10001
- But testing was exercised only for all four values 0,1,2,9999,10000 and 10001. So the coverage is 6/6*100=100%
**So 3 point BVA is always more rigorous than 2 point BVA**

 **Decision Table Testing:**
 - To test system requirements based on the combination and conditions results in different outcomes
 - Effective way to record complex logic such as business rules
 - With decision table the conditions and resulting actions are defined in form of _rows_ and the rules are defined in each _columns_
 - Notations for Decision table, For Conditions **T** for true, **F** for False. For Actions **X** for an action must occur and _Blank_ means it does not occurs.
 - It is a systematic approach to identify all combinations of the conditions.

For example, 
Your favorite bicycle daily rental store has just introduced a new Customer Relationship
Management system and asked you, one of their most loyal members, to test it.
The implemented features are as follows:
 - Anyone can rent a bicycle, but members receive a 20% discount
 - However, if the return deadline is missed, the discount is no longer available
 - After 15 rentals, members get a gift: a T-Shirt

The above example has,
 - Three conditions
    - Being Member - T/F
    - Missed Deadline - T/F
    - 15th Rental - T/F
 - Two actions
    - 20% Discount - X/ _Blank_
    - Get T-shirt - X/ _Blank_

The rules are formed with the conditions. We have two possibilities for any conditions (T/F). So we have 2^(No of conditions) = 2^3=8

So we have 8 rule combinations which are listed in R1 to R8. For every rule, the conditions are filled up with the respective combination and the actions are calculated for the rules and conditions.

|  Conditions  | R1  | R2   |  R3   |  R4   |  R5   |  R6   |  R7   |  R8   |
| ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ | ------------ |
| Being member  |  T   |  T   |  T   |   T  |  F   |  F   |  F   |  F   |
|   Missed Deadline    |  T   |  T   |  F   |   F  |  T   |  T   |  F   |  F   |
| 15th rental        |  T   |  F   |  T   |   F  |  T   |  F   |  T   |  F |
|  Actions
|    20% Discount      |      |      |  X   |   X  |      |      |      |     |
|  Gift T-shirt       |   X  |      |  X   |      |      |      |      | ||




For example R1 states, the person is Being a member and Missed his deadline and it is his 15th rental. Since he missed the deadline, he is not eligible for 20% discount and the action filled with blank. But for his 15th rental he is eligible for Gift tshift which is filled with X.

**State Transition Testing:**
- To showcase all the possible states and state transitions
- _All States Coverage:_ - To make 100% coverage all the states should be visited
- _Valid transitions Coverage:_ Also known as 0-switch coverage. Make sure all the valid transitions are exercised
- _All Transition Coverage:_ Make sure all transitions are covered which included valid and invalid transitions. 

All States coverage is weaker than Valid transition coverage. All transition coverage is better than Valid transition coverage.