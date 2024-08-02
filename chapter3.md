## Static Testing
- It is both validation and verification
- unlike dynamic testing, code need not to be executed
- helps to identify bugs before dynamic testing without test cases
- conducted through,
    - manual examination (reviews)
    - with help of tools (static analysis)

Testing objectives,
- Improve quality
- Detecting defects
- Assessing characteristics like readability, correctness, completeness, testability and consistency
Static analysis incorporated with CI and tools are used (eg. spelling checkers and readability tools)

### Work products tested by Static testing
- Any product can be tested by Static testing
- For Static analysis, the work product needs a structure against they can be tested (e.g json shema checker, spell checker)
- If the work product is not readable by human and cannot be analyzed by static analysis tools, then it cant be tested

### Value of Static testing
- Static testing can unveil defects in early stage which is shift left
- Bug identified in static testing requires less effort and cost rather than bugs discovered in later stages
- By verifying requirements, with the right questions - the quality of the product is improved and the aligns stakeholders in same page
- By verifying the code, the defects in unreachable and non-executable code is discovered

### Dynamic vs Static testing
Both complement each other and have objective to detection of defects. However there are some differences
Static testing:
- Find defects directly - no need to execute the code
- Can also identify defects on unreachable and un executable code
- Measure quality characteristics which are not dependent on executing code

Dynamic testing:
- Find defects from failures while executing the code
- It is applied to executable work product
- Measure quality characteristics which are dependent on executing code

### Defects identified in Static testing
- Requirement defect (duplications, omission, inconsistencies, ambiguities)
- Design defect (inefficient database structures, poor manipulation)
- Coding defect (undefined & undeclared variables, code complexity, duplicate or unreachable code)
- Standard deviation / Violation (Naming conventions)
- Incorrect interface specification (incorrect order of parameters while calling the function)
- Specific type of security vulnerabilities
- Test coverage gaps

### Feedback and review process
**Early and frequent stakeholder review:** 
To prevent misunderstanding and assumption about requirements, it is essential to have early and frequent stakeholder reviews which would reduce the risk of product not meeting the expectation. A failure in this might result in costly rework, missed deadline, blame game and even project failure. 

**Review Process Activities:** 
- **Planning:** To define - Scope of the review, purpose, to item/work product to be reviewed, quality characteristics, areas to focus, exit criteria, standards, time frames and efforts for review 
- **Review initiation:** To define, Everyone involved in review has access to work product, understands the requirement, understands their roles and responsibilities and they have everything to progress with the review
- **Individual review:** Reviewer reviews the work product individually using one or more review techniques like scenario based review, checklist review. The reviewers logs all their identified anomalies, recommendation and questions.
- **Communication and analysis:** Anomalies logged are analyzed and discussed in review meeting to take decision on its status, ownership and required action (whether it is a defect or not)
- **Fixing and Reporting:** From review meeting, the defects are filtered and reported - after the exit criteria, the product is accepted

### Roles and Responsibilities
**Manager:** Decides the product under review, staff involved in it and time of review
**Author:** Creates Product under review and Fixes it if necessary after review
**Moderator:** Also Known as Facilitator. Manages review meeting which includes mediation, time management and a safe environment where everyone can contribute
**Scribe:** Also known as Recorder. Collates and records Anomalies, records review information
**Reviewer:** Performs review. A Subject matter expert or someone from the same team or another team or stakeholder
**Review Leader:** More similar to Manager, Takes overall responsibility of the review process

### Review Types
A product can be reviewed at initial by a Informal process and then by a formal one.
Review types are,
**Informal Review:** Objective - detecting anomalies. Doesn't have a formal process or defined approach
**Walkthrough:** Objective - Evaluating quality of the product, build confident on the build, educate stakeholders, gain consensus, generate new ideas, motivate to find more anomalies. Lead by the author and the reviewers might perform a individual review before walkthrough - which is not mandate
**Technical Review:** Objective - to gain consensus and to take decision on a technical issue. The objective also includes to detect anomalies, evaluate quality, gain confidence, generate ideas and motivate the author to find more anomalies. Led by Moderator and performed by technically qualified reviewers.
**Inspection:** The more formal review. Objective - find more anomalies. Other objectives are similar to tech review and walkthrough which is to evaluate quality, gain confidence, generate ideas and motivate the author to find more anomalies. In Inspection the**Author cannot be a reviewer or scribe**

The diff b/w walkthrough and tech review is, walk through led by author and anyone can perform review. The main focus is to educate the stakeholder/reviewer. Where as the tech review is led by moderator and the main objective is to discuss and decide on a technical issue.

### Success factor for review process
 - Define clear objective and exit criteria. Evaluation of participation should not be an objective
 - Choosing appropriate review type
 - Conduct review in small chunks to avoid the reviewers lost concentration
 - Providing feedback from reviewer to author and stakeholders to improve
 - Providing adequate time for review
 - Support from management
 - Making review part of org's culture
 - Providing adequate training to participants
 - Facilitate meetings