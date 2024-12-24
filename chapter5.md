## Test Planning
### Purpose of Test plan:
 - Documents the means and schedule for achieving test objectives
 - To ensure the test activities meets the criteria
 - Communication tool to team members and stakeholders
 - Demonstrates that testing will adhere to testing policy and strategy (Or explain why it is deviates from them)

Test plan includes, 
- Context of testing
    - scope
    - test objectives
    - constraints
    - test basis
- Assumptions and Constraints of the test project
- Stakeholders (in relevance to testing)
    - Role and responsibilities
    - hiring and training needs
- Communication
    - documentation templates
    - Forms and frequency of communication
- Risk register
    - Project and product risks
- Test Approach
    - Test levels
    - Test types
    - Test techniques
    - Test deliverables
    - Entry and Exit criteria
    - Independence of testing
    - Metrics to be collected
    - Test data requirements
    - Test environment requirements
    - Deviations from organizational test policy and strategy
- Budget and Schedule

### Tester's contribution to Release planning and Iteration planning

Release planning,
- Looks ahead to the release of the product
- Defines and redefines the Product backlog
- May used to refine large user stories into smaller ones
- Basis for test approach and test plan across all iterations
- Tester's contribution towards,
    - Writing testable user stories and define acceptance criteria
    - Participate in Project and quality risk analyses
    - Estimate test effort for user stories
    - Determine test approach and test plan for the release

Iteration planning,
- Looks ahead to the end of the iteration
- Associated with Iteration backlog
- Tester's involved in,
    - Detailed risk analysis of user stories
    - Determine the testability of user stories
    - Break down user stories into testing tasks
    - Estimate test effort for all testing tasks
    - Identify and refine functional and non-functional objectives

### Entry and Exit Criteria

Entry Criteria,
 - Defines preconditions for a given activity
 - In agile, also called as Definition of Ready
 - Includes,
    - Availability of resources like people, tools, environment, budget, time
    - Availability of testware like test basis, testable requirements, user stories, test cases
    - Initial level of a test object like all smoke tests should be passed


 Exit Criteria,
 - Defines what must be achieved to declare an activity is completed
 - In agile, also called as Definition of Done
 - Includes,
    - Measures of thoroughness like achieved level of coverage, number of unresolved defects, defect density, number of failed test cases
    - Completion criteria like planned tests have been executed, static testing has been performed, all defects found are reported, all regression tests are performed
 - Example - Running out of time or budget is valid exit criteria, so even without satisfying other exit criteria's and with approval from stakeholders, the product can go live without further testing


### Estimation Techniques
- Predicting the amount of test related work needed to meet the objectives of test project
- It is important to make it clear to stakeholders that the estimation is based on assumptions and it can be subject to error
- Estimating smaller tasks is accurate comparing to larger tasks, Therefore chop large tasks into smaller ones and estimate

#### Estimation based on ratios
 - Metrics based technique
 - Retrieve the metrics within the organization from similar project
 - Use the ratio for the effort for estimation. For example, if the organization's previous project or metrics data has 3:2 ratio for development to test effort, use the same.
 - Example, Organizations development-to-test effort ration 3:1 and development effort estimated for current project as 300 hours, then testing effort is 1/3 of development effort which is 100 hours.

#### Extrapolation
 - Metrics based technique
 - Observe and Gather data from early iterations of the project. Use the data gathered to estimate the remaining effort by extrapolating the data.
 - Suitable for iterative SDLC as the testing effort would be average of previous iterations effort
 - Example, Testing effort for previous iterations 3 days for 8 user stories, 4 days for 16 user stories and 2 days for 6 user stories. If we sum all the efforts it is 9 days for 30 user stories. So per user story it is 30/9= 0.3 days. Extrapolating this information for next iteration as if we have 10 user stories, then the effort would 10*0.3 = 3 days.

 #### Wideband Delphi
 - Iterative, expert-based technique
 - Experts estimates the effort for an item individually in isolation. Then they group together to discuss their estimation. Based on feedback, each expert redo the estimation in isolation, individually.  This process is repeated until the everyone agrees for an estimation.
 - Example Planning poker - where the cards represented in effort size. For each tasks, the team goes through the items to be done and estimate the effort required individually, then collects each ones estimate - if there are difference between individuals estimation then they would explain the reason for the estimation and the process repeated until everyone agrees to a particular estimate

 #### Three-point estimation
 - Expert based technique
 - It is calculated with experts estimation inputs for
    - most optimistic estimation (a)
    - most likely estimation (m)
    - most pessimistic estimation (b)
 - Formula Estimation (E) = (a+ 4*m +b)/6
 - Formula for measurement error (SD) = (b-a)/6
 - Example, for A project a=6, m=9 and b=18 then, E=(6 + 4*9 + 18)/6 = 10. SD = (18-6)/6 = 2. So the estimation is 10~2 hours.

### Test Case Prioritization
- Test case prioritization - defining the order of running the test cases and test procedures after they assembled into test suites
- Prioritization techniques:
    - Risk based prioritization: Tests with most important risks executed first - Order of execution defined based on the risk analysis
    - Coverage based prioritization: Test cases with high coverage executed first
    - Requirement based prioritization: Test cases mapped to high priority requirements executed first - Priority of requirements defined by Stakeholders
- There are some exceptions. For example, if the Test case with higher priority is dependent of test case with lower priority, then the test case for lower priority must executed first to fulfill the dependency.
- Order of priority must also considered based on resources

### Test Pyramid
- It is model showing different tests having different granularity
- Each layer represent group of tests, higher the layer lower granularity
- Bottom layer contains mostly small, isolated and fast tests which checks small functionality. Lot of them require for coverage
- Top layer contains end to end tests, slower than lower layers which checks large functionality. Few of them require for coverage
- Original test pyramid layers: Unit tests, service tests and UI tests
- Another model defines each layer as Unit (component) tests, Integration tests and end-to-end tests

### Testing Quadrants
- Groups the tests into different test levels with the appropriate test types, activities, test techniques and work products
- Test management by visualizing tests 
- Helps to differentiate and describe different type of tests to stakeholders
- Tests can be business facing or technology facing, Tests can also be support the team or critique the product. 
- Four quadrants:
    - Q1: Technology facing, support the team - component and component integration tests - Tests should be automated and included in CI
    - Q2: Business facing, support the team - functional tests, Checks the acceptance criteria - Can be automated or manual
    - Q3: Business facing, critique the product - Exploratory testing, usability and user acceptance testing - Manual
    - Q4: Technology facing, critique the product - smoke and non functional tests - Automated

## Risk Management
Main activities of Risk management:
- Risk analysis: Risk identification and assessment
- Risk control: Risk mitigation and monitoring
Risk-based testing: Test approach where the test activities are identified, prioritized and managed based on risk analysis and risk control

Risk:
 - A potential event, hazard, threat or situation which causes adverse effect. Categorized into two factors which defines risk level (measurement of risk)
    - Risk likelihood: Probability of risk occurrence
    - Risk impact: consequence of risk occurrence 
 - Higher the risk level the more important is its treatment

Types of risks in Software:
- Project Risks: Related to management and control of the project. This includes,
    - Organizational Risks (Delays in work product delivery, inaccurate estimates, cost-cutting)
    - People issues (insufficient skills, conflicts, communication problems, shortage of staff)
    - Technical issues (scope creep, poor tool support)
    - Supplier issues (third party delivery failure, bankruptcy of supplier company)
- Product Risks: Related to Product quality. Examples,
    - missing or wrong functionality, incorrect calculations, runtime error, poor architecture, inefficient algorithms, inadequate response time, poor user experience, security vulnerabilities
    - In would result in negative consequences like,
        - User dissatisfaction
        - Loss of revenue, trust, reputation
        - Damage to third parties
        - High maintenance costs, overload of helpdesk
        - Criminal penalties
        - In extreme cases, physical damage, injuries or even death.
### Product Risk Analysis:
 - From testing point of view, The testing effort should be focused to provide awareness of a risk to minimize the residual level of a risk.
 - It should be in early cycles of SDLC
 - Project Risk Analysis,
    - Risk Identification: Generating comprehensive list of risks
    - Risk Assessment: Categorization of identified risks
        - With this we can assign mitigation steps and risks in category might be resolved with same mitigation
        - Can be qualitative or quantitative approach or mix of both
        - Qualitative approach: using risk matrix, Quantitative approach: Multiplication of Risk likelihood and risk impact
 - It may influence thoroughness and scope of testing. The risk analysis results are used to,
    - Determine scope of testing carried out
    - Determine particular test levels and Propose test types to be performed
    - Determine the testing techniques to be employed and coverage to be achieved
    - Estimate test effort required for each task
    - Prioritize testing effort to find critical bugs as soon as possible
    - Determine to include the additional tests to explore risks on the product
### Product Risk Control:
 - All measures taken in response to identified and assessed product risks
 - Risk Mitigation: Implementing the actions proposed in risk assessment to reduce the risk
 - Risk Monitoring: to make to mitigation actions are effective, to obtain more information to improve risk assessment and to identify emerging risks
 - From testing mitigation steps for a risk are,
    - Select the testers with right level of skills and expertise, suitable for a given risk type
    - Apply an appropriate level of independence of testing
    - Conduct reviews and perform static analysis
    - Apply appropriate test technique and coverage levels
    - Apply the appropriate test types addressing the quality characteristics
    - Perform dynamic testing, including regression testing

## Test monitoring, Test Control and Test Completion
 - Test monitoring: Gathering information about testing to access the testing progress and measure the exit criteria associated with coverage of product risk, acceptance criteria and requirements
 - Test Control: Control directives, corrective measures and guidance to achieve efficient and effective testing with the Test monitoring information. Actions are,
    - RePrioritize the tests
    - Reevaluvate the exit criteria
    - Adjust test schedule and address the delay in test environment
    - Add resources where its needed
 - Test Completion: To Collect data from completed test activities to consolidate the experience, testware and other relevant information.

### Metrics used in Testing:
 - Test metrics are collected,
    - To show progress against the planned schedule and budget
    - To understand the Current quality of the product
    - To know the Effectiveness of the test activities against the objective
    - Against the iteration goal
 - Different Test metrics,
    - Project progress metrics
    - Test progress metrics
    - Product quality metrics
    - Defect metrics
    - Risk metrics
    - Coverage metrics
    - Cost metrics
 - Testing report summarizes and communicates the test information during and after testing.
 - Test progress report: Generated on regular basis to keep the stakeholders informed about the testing process and share information to make corrective measure due to deviation from the plan
 - Test completion report: Prepared during test completion when exit criteria is met.
 
 ### Communicating the Testing stages:
  - Communication should be tailored 
  - One or multiple forms can be used 
  - Options,
    - Verbal communication,
    - Dashboards,
    - Electronic communication,
    - Online Documentation,
    - Test Reports

## Defect Management:
 - One of major objective of testing is to identify defects
 - An established defect management process is essential
 - Anomalies can be reported on any stages and any of form of SDLC
 - Log the reported anomalies, Analyze and classify - Find fix or keep it as it is and finally close the Defect Report
 
 Defect report should have,
 - Responsible person to handle and fix the issue reported with sufficient information about the issue
 - Provide means of tracking the quality of the product
 - Provide ideas for improvements on test and development process

 A Defect report logged with dynamic testing includes,
 - Unique ID
 - Title in short summary about the defect
 - Date when anomaly was observed, issuing organization, author and their role
 - Test object and test environment
 - Context of the defect (test case, SDLC phase,test tech, test type and etc)
 - Description of the failure, reproducible steps, logs, screenshots and recording
 - Expected and actual result
 - Severity of the defect
 - Priority
 - Status of the defect
 - References

