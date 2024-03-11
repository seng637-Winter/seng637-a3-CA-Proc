**SENG 637 - Dependability and Reliability of Software Systems**

**Lab. Report #3 – Code Coverage, Adequacy Criteria and Test Case Correlation**

| Group \#: 5      |     |
| -------------- | --- |
| Student Names: |     |
| Christopher Brunet |     |
| Christopher Proc |     |
| Sean Buchanan |     |

(Note that some labs require individual reports while others require one report
for each group. Please see each lab document for details.)

# 1 Introduction

The purpose of Lab 3 is to conduct white-box testing using code coverage tools in order to learn and demonstrate the ability to plan, execute, and evaluate a comprehensive test suite on a function System Under Test (SUT). We will build upon the test suite that was created during Lab 2, and continue expand the coverage of our test suite against the JFreeChart package as our SUT. 

# 2 Manual data-flow coverage calculations for DataUtilities.calculateColumnTotal and Range.getLength methods.

This section outlines the manual analysis of two methods, DataUtilities.calculateColumnTotal(), and Range.getLength(). Each method was manually evaluated on a line-by-line basis in order to build a Data Flow Graph, D-U pair list for each variable, and then we evaluated the coverage of our Lab 2 test cases. 

## Analysis of DataUtilities.calculateColumnTotal()

#### Data Flow Graph:

![Data Flow Graph](.\media\CalculateColumnTotalDFG.png)

#### Definitions and Uses in each statement:
| Statement| Defined| Used|
|-----|-----|-----|
|0|data, column| |
|1| | data|
|2| total| | 
|3| rowCount| data|
|4| r| rowcount, r|
|5| n| data, r, column|
|6| | n| 
|7| total | n|
|8| r2| rowCount, r2|
|9| n| data, r2, column|
|10| | n|
|11| total | n|
|12| | total|

#### D-U Pairs by Variable:
| Variable | Pairs |
|----- | ----- |
| data | (0,1), (0,3), (0,5), (0,9) | 
| column | (0,5), (0,9)|
| total| (2,12), (7,12), (11,12) |
|rowCount|(3,4), (3,8) |
|r|(4,5)|
|n| (5,6), (5,7), (9,10), (9,11)|
|r2| (8,9)| 

#### Test Case D-U Coverage:
| Test Case| Covered D-U Pairs|
| ----- | ----- | 
| calculateColumnTotalNullDataShouldThrowException()| data (0,1)|
| calculateColumnTotalOfColumn0ShouldReturn3()| Data ((0,1), (0,3), (0,5), (0,9)), column ((0,5)), total ((7,12)), rowCount ((3,4), (3,8)), r (4,5), n ((5,6), (5,7)) |
|calculateColumnTotalOfColumn1ShouldReturn0()| Data ((0,1), (0,3), (0,5), (0,9)), column ((0,5)), total ((7,12)), rowCount ((3,4), (3,8)), r (4,5), n ((5,6), (5,7)) |
| calculateColumnTotalOfColumn2ShouldReturn3()|Data ((0,1), (0,3), (0,5), (0,9)), column ((0,5)), total ((7,12)), rowCount ((3,4), (3,8)), r (4,5), n ((5,6), (5,7)) |
|belowZeroColumnShouldThrowException()| column (0,5)|
|aboveColumnCountColumnShouldThrowException()| column (0,5)|
|Not Tested| column (0,9), total ((2,12), (11,12)), r2 (8,9), n ((9,10), (9,11))|

<b>Total D-U Coverage: 11/17 D-U Pairs = 64.7%</b>

## Analysis of Range.getLength():

#### Data Flow Graph:

![Data Flow Graph](.\media\getLengthCFG.png)

#### Definitions and Uses in each statement:
| Statement| Defined| Used|
|-----|-----|-----|
|0| lower, upper| |
|1| | lower, upper|
|2| msg| | 
|3| | msg|
|4| | lower, upper|

#### D-U Pairs by Variable:
| Variable | Pairs |
|----- | ----- |
|lower| (0,1), (0,4)|
|upper| (0,1), (0,4)|
|msg| (2,3)|

#### Test Case D-U Coverage:
| Test Case| Covered D-U Pairs|
| ----- | ----- | 
|getLengthPosPosRange()| lower((0,1), (0,4)), upper ((0,1), (0,4)) |
|getLengthZeroPosRange()| lower((0,1), (0,4)), upper ((0,1), (0,4)) |
|getLengthNegZeroRange() | lower((0,1), (0,4)), upper ((0,1), (0,4)) |
|getLengthNegNegRange()| lower((0,1), (0,4)), upper ((0,1), (0,4)) |
|getLengthNegPosRange()| lower((0,1), (0,4)), upper ((0,1), (0,4)) |
|getLengthZeroLengthRange()| lower((0,1), (0,4)), upper ((0,1), (0,4)) |
|getLengthInfInfRange()| lower((0,1), (0,4)), upper ((0,1), (0,4)) |
| Not Tested| msg(2,3)|

<b>Total D-U coverage: 4/5 = 80%</b>

# 3 A detailed description of the testing strategy for the new unit test

## 1. Test Strategy
### Scope of Testing
All testing will be done on the SUT, JFreeChart version 1.0.19
#### Features to be tested
    Testing will be limited to all methods included in:
    -  org.jfree.data.DataUtilities
    -  org.jfree.data.Range

#### Features not to be tested
    Testing excludes all methods and classes included within JFreeChart that are not listed above. 

### Type of Testing    
    Unit Testing - White Box.

    Testers will have access to inspect source code.

### Who will test
    Test case design and implementation will be split evenly between the three group members.

## 2. Test Objective
    The objective of this test plan is to analyze the current coverage of the SUT and features to be tested against three metrics:
    - Statement Coverage
    - Branch Coverage
    - Condition Coverage

    Testers will then enhance the current test suite with enough test cases to ensure that we have achieved a high level of coverage across all three metrics for each of the two selected classes. Testers should use best judgement and careful analysis in order to select test cases which maximize the coverage per test case in order to efficiently accomplish this test plan.

    General guidance is to first develop comprehensive unit tests for all untested methods. Then conduct further analysis in order to see where further coverage is needed. 
## 3. Test Criteria
    This test phase will be considered successful when the two featured classes achieve the following metrics: 
    - 90% Statement Coverage
    - 70% Branch Coverage
    - 60% Condition Coverage.

## 4. Deliverables

    Testers will deliver: 
    - functioning source code which encompasses the test runner, and all of the individual unit tests for the Range and DataUtilities classes, specifically.
    - An analysis of the final coverage of the classes under test.
    - A detailed description of five individual unit tests
    - A report on the execution of the test plan.

# 4 A high level description of five selected test cases you have designed using coverage information, and how they have increased code coverage

Text…

# 5 A detailed report of the coverage achieved of each class and method (a screen shot from the code cover results in green and red color would suffice)

Text…

# 6 Pros and Cons of coverage tools used and Metrics you report

### EclEmma

#### Pros
#### Cons

# 7 A comparison on the advantages and disadvantages of requirements-based test generation and coverage-based test generation.

- Talk about how coverage-based test generation doesn't necessarily determine if the code is meeting the requirements.
# 8 A discussion on how the team work/effort was divided and managed

Text…

# 9 Any difficulties encountered, challenges overcome, and lessons learned from performing the lab

Difficulties and Challenges:
- Managing iterative java projects with verions with different dependencies

Lessons Learned:
- Importance of keeping test suites neat and well commented (Abililty to find tests for the methods you're interested in)


# 10 Comments/feedback on the lab itself

- Really liked the effort that was put into the setup instructions. 
