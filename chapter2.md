### Chapter 2
## SDLC - Introduction
Software Development Life Cycle is an abstract and high level representation of software development process. It defines,
- each development process
- types of activities on each process and relation b/w each other logically and chronologically
- Testing must be adapted for the success of SDLC

#### Development model example and importance of Testing
- **Sequential Development model**: 
    \
Testers involved in initial phases and participate in requirement reviews, test analysis and test design. Static testing from initial phases.Dynamic testing cannot be done in initial phases as executable code created in later phase. Example,
    - Waterfall
    - V-model
- **Iterative Development model**: 
\
Each iteration produces working prototype or product increment. Both Static and Dynamic testing is possible in each phase of SDLC. Requires Fast feedback and Extension regression testing. Example,
    - Spiral modelling
    - Prototyping
- **Incremental development model**: 
\
Same as Iterative development method. Example,
    - Unified process

Some of the SDLC activities can be described in detail by,
\
- Details software development methods
- Agile practices

**Development methods**,

    - ATDD: Acceptance Test Driven Development
    - BDD: Behavior Driven Development
    - DDD: Domain Driven Development
    - EP: Extreme Programming
    - FDD: Feature Driven Development
    - TDD: Test Driven Development
\
**Agile practices**,
    
    - Kanban
    - Lean IT
    - Scrum
 

In Agile, change occur at anytime - So extensive test automation is required to ease up the regression testing. Also manual testing to be done using experience based test technique that does not require prior test analysis and design (The tester more familiar with the product and so he/she need lesser time understand the requirement and perform testing for experienced test technique) \

## SDLC and Good Testing Practices
Irrespective of the SDLC model,
- For every development activity there should be a corresponding testing activity
- Different test levels have different test objectives - So the redundancy is reduced. 
- Test analysis and design should begin to the corresponding development phase - adhere with Early testing
- Testers should start review as soon as the work product available - shift left approach

To summarize, each development activity should have a testing activity. The testing activity should have a defined test objective. The testing analysis and design should begin in parallel to the SDLC corresponding activity and the testing should start as soon as the product/executable is ready. \

## Testing as a Driver for SDLC
- Test are defined to drive Development
- Implements Early testing principle and shift left approach
- Supports Iterative development model

Development methods,

**TDD (Test Driven Development)**: Directs coding through test cases. Write code first - develop code for Tests - refactor code and test as needed

**ATDD (Acceptance test driven development)**: Tests are derived from acceptance criteria drives the development. Test cases written before application development and Code written to satisfy the test cases.

**BDD (Behavior Driven Development)**: Tests are written on the basis of application behavior in Given/When/Then format - Example, GIVEN the user on facebook page --> WHEN the user clicks on like button --> THEN the Like count increased 

### Devops and Testing:
DevOps,
 - Organization approach where Development and Operations works together to achieve common goals
 - Cultural shift within organization to reduce the gap between Development (including testing) and Operations
 - Enables teams to Build, test and release high-quality code using delivery pipeline
 From testing perspective,
 Benefits:
 - The application code would be moved from one stage to another (eg. Development -> Staging/QE Environment -> Production Environment) through the well defined pipeline process. For each stage, the automated regression test scripts can be created and checkpoints can be defined. So If there is a bug on the code which would impact the existing functionality, that could be easily discovered with the automated regression tests. These regression tests can be unit tests, component tests, integration tests or E2E tests. Thus faster feedback and quality code.
 - It promotes shift left approach as the Developer has to create and maintain unit and component tests along with static analysis
 - Ensures environment stability as the faulty code will not be promoted to one stage to another if the check point is not completed
 - Reduced manual testing for regression and risk of regression bugs is minimized
 Disadvantage:
- The pipeline needs to be defined and established
- Test Automation creation and maintenance is difficult
- Manual testing is still needed 

### Shift-left approach
Shift-left == Early testing, testing performed at the early stages of SDLC, instead of waiting for the code to be implemented and components to integrated. Testing later is not neglected.
 - Reviewing the specs of product from the testing perspective - it find potential bugs, inconsistencies, incompleteness and ambiguities
 - Write tests before code and have the test running against code to make sure it works per expectation
 - Use CI/CD (Continuous Integration and Continuous deployment) to faster feedback
 - Complete Static testing before dynamic testing
 - Perform non-functional test also at the early stage as possible

 ### Retrospectives and Process improvement
 Retrospective - Held at the end of the project or iteration or release milestone or when needed. The results are recorded in Test Completion report. Items under discussion,
 - What is successful and to be retained
 - What is not successful and could be improved
 - How to improve bad ones and retain good ones
It benefits testing by,
- Increased test effectiveness and efficiency
- Improved quality
- Better team collaboration, team bonding and learning

### Test levels and types
Test Levels - Different testing activities organized and managed together. Each level has Entry and exit criteria, which might not be define for iterative model.

Five test levels,
#### Component Testing: 
- Unit testing
- Test components in isolation 
- Test harness and unit testing frameworks needed to perform
- Performed in development environment

#### Component Integration Testing:
- Unit integration testing
- Testing interfaces and interaction between components
- Depends on integration strategies like bottom-up, top-down and big-bang

#### System Testing:
- Testing on Overall behavior and capabilities of the entire product
- Functional testing of end to end tasks and Non functional testing of product characteristics
- Performed by independent testing team
- Non functional testing preferably performed on a complete system in a representative test environment

#### System Integration Testing:
- Testing interfaces of the system under test and other system and external services
- Test environment should be similar to production/operational environment

#### Acceptance Testing:
- Test whether the system fulfills user needs which is Validation
- Make sure the system ready for deployment to production for customer use
- Ideally Performed by intended users (Customers)
- Main forms of Acceptance testing are
    1. User acceptance testing (UAT) - Testing for end user satisfaction
    2. Operational acceptance testing - Testing for Products robustness on real world conditions
    3. Contractual and regulatory acceptance testing - Testing against the agreements on the contracts and regulations
    4. Alpha testing - Performed by testers of the organization using black and white box techniques at the end of development. Moto - Whether product work?
    5. Beta testing - Performed by real users/ external tester using black box technique. Moto - Whether user likes the product?

All the above activities are differentiated by their the below attributes
 - Test objectives
 - Test object
 - Test basis
 - Defects and Failures
 - Approach and responsibilities

 For each test level, the definition of above attributes will differ

 ### Test Types:
Four Test types,

 #### Functional Testing: 
 - To evaluate the functions that component and system should perform
 - Test for "What the product should do"
 - Tests functional completeness, functional correctness and functional appropriateness

 #### Non-Functional Testing:
 - Test for "How well system behaves"
 - Tests non-functional quality characteristics - Performance, Compatibility, Usability, Reliability, Security, Maintainability and Portability
 - Many non-functional tests derived from functional tests, the only difference is - functional tests checks for the "what the product do", where as the non functional tests checks "what the product do in a specified constraints" like time, payload, platform and etc
 - It sometimes needs a specific environments as well. Eg - Usability tab for usability testing

 #### Blackbox Testing:
 - Specification based
 - Derives tests from documentations (like Requirements)
 - Moto: Check system behavior against the specification on the documentation

 #### Whitebox Testing:
 - Structure based
 - Derives tests from systems's implementation or internal structure
 - Moto: Check the structure of the system by the tests to the accepted level

These testing types are applicable for all test levels - But the focus of each type on the system varies on each level.

 Apart from the above, we also have
 #### Confirmation Testing: 
 - Confirms original defect has been fixed
 - Can be carried out by, executing the failed tests for the bug and creating new tests for the bug.
 - But during the time or money constraints - The confirmation testing simply performed to reproduce the bug and to confirm the bug is not occured
 - Performed at all levels when the there is fix or code change

 #### Regression Testing:
 - Confirms existing components are not impacted with the a bug fix (which might be verified with confirmation testing)
 - The existing components can be part of same system or other systems integrated 
 - First perform Impact analysis before accepting a change or fix to a system. Impact analysis would help us to identify the components or system impacted by the fix or change. With that, regression testing can be extended to cover the impacted components
 - Strong candidate for automation
 - Number of regression tests increases for each iteration or release
 - As mentioned in Devops section above, the CI would incorporated with Automated Regression tests for faster feedback and improved product quality
 - Performed at all levels when the there is fix or code change

#### Maintenance Testing:
- Performed when changes to Environment or maintenance activities to confirm the product is not impacted
- Ensures the product is functional and reliable after maintenance activities
- Maintenance can be of corrective, adaptive changes in the environment or performance improvement or maintenance of the environment
- Maintenance testing performed after,
    - Modifications - planned (release based) and unplanned (hot fixes)
    - Upgrades - Eg, upgrading platform from one to another
    - Retirement - Application reaches end of life cycle
- Scope of maintenance testing depends on Risk of the change, size of the existing system and size of the change