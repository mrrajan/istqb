### Chapter - 1 
## Software testing

-  Increases the quality and reduces the risk of software failure in operations
-  It is set of activities to discover defects and elevates the quality of the software artifacts
-  Not only a tech activity, it properly planned, managed, estimated, monitored and controlled
-  It is a intellectual activity which requires testers to have specified knowledge, analytical skills and apply critical thinking and systems thinking

*Verification:* Checking whether the system meets the requirement \
*Validation:* Checking whether the system meets the need

## Test Objectives
 - Evaluating work products such as req, user stories, design and code
 - Ensuring required coverage of the test object. Ensuring the test object compiles with contractual, legal and regulatory requirements
 - triggering failures and finding bugs
 - Verify test object meets specific requirements and works per stakeholders expectation
 - Reducing the level of risk of in the software quality and Building confidence in the quality of the product

## Testing vs Debugging
 - Testing: Finding defects (stating testing) or triggering failures caused by defects (dynamic testing) example: finding a dent in a car vs NCAP rating (triggering car accident find the safety rating)
 - Debugging: Finding cause of the failure\
	- On Dynamic testing if a failure occurs (example: The chassis of the car not designed caused the maximum damage) debugging would follows as,
    	- Reproducing the failure
    	- Diagnosis (find the root cause)
    	- Fix the failure
    - On Static testing if a defect identified (Failures not occurred on Static testing as we are not executing anything example - scratch on a car or crack on windshield), the debugging steps are
	    - No need to reproduce the failure
		- No need for Diagnosis
		- Directly fix the issue

## QA vs QC
 - QC Product oriented - Corrective approach which focuses on the achievement of quality - Major form of testing - Test results to Fix defects
 - QA Process oriented - preventive approach which focuses on implementation and improvement of a process - responsibility of every stakeholder - Test results is a feedback on how well processes(Testing and development) are performing
 

## Errors vs Defects vs Failures
- Error: Mistakes made by human, root cause for faults, bugs, defects and failures. Various reasons,
    - Time
    - Pressure
    - Product complexity
    - Lack of training
    - Tired and fatigue
- Defects: Can be found in documentation, such as below. Defecting artifact often cause failure.
    - In Requirements
	- In product source code
	- In supporting artifacts
- Failures: Errors and Defects are one of the root causes, A failure can happen due to environmental condition as well

- Root cause - The fundamental reason for defect or failure, removing the root cause the defect or failure may not occur again

## Testing Principles
1. Shows defect and not the absence: Cannot prove a product has zero defects, Testing reduces the possibility of defects remains undiscovered
2. Exhaustive testing is impossible: No way to test a product 100%
3. Test early to save money and time: Early discovering of defect reduces the cost of fixing and time 
4. Defects cluster together: Pareto principle - a small portion of a system contributes for a most of the defects - if you find a bug on a component, possibility that it has more
5. Tests wears out: Repeated tests are ineffective - modify the test case and test data once in a while
6. Testing is context dependent: There is no universal approach for all testing - testing method and ways changes based on what you test
7. Absence of defects fallacy: Fallacy means misconception, as the word states verification will just ensure whether the product meets the requirement with reduced occurrence of failure. But it does not promise the product meets customer needs. So Not just Verification, Validation also should be carried out.

## Test Activities and Tasks
 Testing is context dependent - which means the testing methods and ways might vary for what you test. But there are set of activities which needs to be aligned in order to achieve test objectives. These set of activities are like templates which needs to be configured based on the product which we test.\
 \
 These activities can be run in parallel or in iterative (one after another)
- *Test Planning*: Defining test objectives and selecting approach to achieve test objectives
- *Test monitoring and Control:* Monitoring the overall process and progress, comparing it against the plan
- *Test Analysis:* Answers "What to test?" To identify testable features, to define and prioritize --> test conditions, related risks and risk levels. 
- *Test design:* Defines "How to test?" To define the test cases from test conditions. It severs as a guide to specify test inputs
- *Test implementation:* Creating and acquiring testware for testing. This includes Organizing test cases into test procedures(also known as test instances) and grouped into test suites and they are prioritized. Preparing test data and test environment. Creating manual and automated test scripts to support execution
- *Test execution:* Running tests according to test execution schedule and priority. Compare the test results to the expected result and report anomalies after analysis 
- *Test completion:* Occurs at project milestones (End of release, iteration). If the defects are unresolved, then either change request or project backlog created. Testware suitable for next iteration identified and kept alive and others would be shut down. The Test completion report would be shared to stakeholders

## Skill for testing
 - Testing knowledge, Domain Knowledge and technical knowledge
 - Thoroughness, carefulness, curiosity, attention to detail and being methodful
 - Analytical thinking, critical thinking, Creativity
 - Good communication skill, Active listening and team player

 
## Whole team approach
- Practice coming from Extreme programming 
- Everyone is responsible for quality
- Anyone with adequate skill and knowledge can perform any task
## Independence of testing
- The testing carried out by other than developer (author) of the code. More degrees of independence proportional to more defects identified. So if the code is been tested by the developer, very lesser chance to identify bugs.But if we involve persons who is not related to any of the background about the code (but with product and domain knowledge) then there is a higher chance in finding defects
- Drawbacks: 
	- Independent testers isolated from Developer which causes communication, collaboration and adversarial relationship issues
	- Developers may lose the responsibility of testing as other team would verify the product for requirement
	- It is kind of bottleneck (obstructing the release or slowness in testing) and blamed for delays in release. This caused due to the independent testers might not aware of the background of the product and totally dependents of documentation. Which might results in communication and knowledge gap which extends the testing process. Causing slowness in progress and obstruction in product release
