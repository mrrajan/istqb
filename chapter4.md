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

### Whitebox technique:
**Statement Testing:**
- To ensure each executable statement is tested atleast once

Example,
```
def check_value(x):
    if x > 0:
        print("Positive number")
    else:
        print("Non-positive number")
```        
Test case 1: x=5
Test case 2: x=-1

In the above example, the executable statements if x>0 and else has been tested atleast once. But this testing will not ensure the testing of all decision logics and may not detect all the defects.

***Statement Coverage:***
- Measurement of test case coverage for total number of executable statements
- Statement coverage = (No of statements executed/ Total no of statement) * 100

**Branch Testing:**
- Control flow graph is used to define all possible sequences in a source code execution
- Branch is a transfer of control between two nodes in a control flow graph
- Branching is caused by conditional statements like if, else, while, for, switch
In the statement testing example above, there are infinite possibilities for value 'x'. But the branching occurs when the value if greater than or lesser than zero.

***Branch coverage:***
- Branch coverage = (No of branches executed/ Total no of branches)* 100

Branch coverage subsumes Statement coverage. So 100% Branch Coverage guarantees 100% Statement coverage. But 100% Statement coverage is not 100% branch coverage.

### Experience-based technique ###
**Error Guessing:**
- To anticipate for errors, defects and failures based on tester's experience
- This is possible as tester know about - how the application worked in the past, types of errors developers tend to make and similar issues occurred on another applications.
- Errors, Defects and Failures occurs due to
    - Input (Valid input not accepted, parameters wrong or missing)
    - Output (Wrong format, wrong result)
    - Logic (Missing cases, wrong operator)
    - Computation (wrong computation, missing operand)
    - interfaces (parameter mismatch, incompatible types)
    - data (incorrect initialization, wrong type)

*Fault attacks* are a methodological approach to the implementation of error guessing. The tester creates tests based on a list of possible errors, defects and failures to test a system with their experience, an existing defect, failure data and common knowledge.

**Exploratory Testing**
- Tests are simultaneously designed, executed and evaluated while the tester learns about the application. 
- To explore the test application more deeply with focused tests and to create tests for untested areas
- Sometimes, Conducted within a defined time-box on session based approach.
- Exploratory testing is useful when *few or inadequate specification or there is significant time pressure* for testing
- It also complements and incorporate other testing techniques
- Effective when the tests is experience, has domain knowledge and has a high degree of skills 

**Checklist-based Testing**
- Testing carried out with the list of checklists
- Checklists are formed with experience and knowledge of the user or an understanding of how and why a software fails
- Items better suited as Entry/exit criteria or items that are too general
- In the absence of test cases, checklists can provide a degree of consistency for testing
- Checklist can be a form of question and may refer a requirement, quality characteristics or any other form of test conditions
- Checklists needs to be updated based on defect analysis as the testing may ineffective over a period of time
- Make sure the checklist is not become too long!

### Collaborative-based technique ###
- Defect avoidance by collaboration and communication

**Collaborative userstory writing**
- User story represent a feature which is valuable for a user or purchase of a system or software
- Three critical aspects
    - Card - Medium to describe user story. Includes a title and short description of the requirement
    - Conversation - Discussion between stakeholders, developer and testers to understand and elaborate the user story
    - Communication - Acceptance criteria for the end product
- Can be done using brainstorming and mind mapping
- This sets a shared vision of what should be delivered by considering business, development and testing perspectives
- Good user stories should be INVEST
    - Independent
    - Negotiable
    - Valuable
    - Estimable
    - Small
    - Testable
If any of these missing, it is not a good user story

**Acceptance Criteria**
- Acceptance criteria are the conditions that an implementation (end product/ software) of the user story must meet to be accepted by stakeholders for an user story 
- From testing perspective, Acceptance criteria is the testing conditions should be exercised by Tests
- Acceptance criteria is the result of conversation on a user story
- This is used to,
    - Define scope for user story
    - Reach consensus among stake holders
    - Describe both positive and negative scenarios
    - Serve as a basis for User story acceptance testing
    - Allow accurate planning and estimation
Two common formats for acceptance criteria definition
- Scenario oriented (Given/ When/ Then from BDD)
- Rule oriented (bullet point verification list or tabulated form of input output mapping)

**Acceptance Test driven development**
- ATDD is a test first approach
- Test cases are created prior to implementing (develop) the user story with  different perspectives - customer, developer and tester
- It can be manual or automated
- First step is a specification of workshop where user story and its acceptance criteria is defined and discussed
- Next step create test cases from the acceptance criteria
- No two test cases should describe same characteristics of user story
- Typically start with positive tests and perform negative testing. Finally uncover the non-functional characteristics like performance, load and etc
- When the test are captured in automated framework supported format (like a feature file), the developer can implement automated tests which become executable requirements.
