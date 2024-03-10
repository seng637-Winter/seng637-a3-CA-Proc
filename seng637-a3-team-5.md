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

Text…

# 2 Manual data-flow coverage calculations for DataUtilities.calculateColumnTotal and Y methods

calculateColumnTotal

Data Flow Graph:
![Data Flow Graph](.\media\CalculateColumnTotalDFG.png)

Def-Use per statement:
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

Def-Use Pairs by Variable:
| Variable | Pairs |
|----- | ----- |
| data | (0,1), (0,3), (0,5), (0,9) | 
| column | (0,5), (0,9)|
| total| (2,12), (7,12), (11,12) |
|rowCount|(3,4), (3,8) |
|r|(4,5)|
|n| (5,6), (5,7), (9,10), (9,11)|
|r2| (8,9)| 

Test Case D-U Coverage:
| Test Case| Covered D-U Pairs|
| ----- | ----- | 
| calculateColumnTotalNullDataShouldThrowException()| data (0,1)|
| calculateColumnTotalOfColumn0ShouldReturn3()| Data ((0,1), (0,3), (0,5), (0,9)), column ((0,5)), total ((7,12)), rowCount ((3,4), (3,8)), r (4,5), n ((5,6), (5,7)) |
|calculateColumnTotalOfColumn1ShouldReturn0()| Data ((0,1), (0,3), (0,5), (0,9)), column ((0,5)), total ((7,12)), rowCount ((3,4), (3,8)), r (4,5), n ((5,6), (5,7)) |
| calculateColumnTotalOfColumn2ShouldReturn3()|Data ((0,1), (0,3), (0,5), (0,9)), column ((0,5)), total ((7,12)), rowCount ((3,4), (3,8)), r (4,5), n ((5,6), (5,7)) |
|belowZeroColumnShouldThrowException()| column (0,5)|
|aboveColumnCountColumnShouldThrowException()| column (0,5)|


# 3 A detailed description of the testing strategy for the new unit test

Text…

# 4 A high level description of five selected test cases you have designed using coverage information, and how they have increased code coverage

Text…

# 5 A detailed report of the coverage achieved of each class and method (a screen shot from the code cover results in green and red color would suffice)

Text…

# 6 Pros and Cons of coverage tools used and Metrics you report

Text…

# 7 A comparison on the advantages and disadvantages of requirements-based test generation and coverage-based test generation.

Text…

# 8 A discussion on how the team work/effort was divided and managed

Text…

# 9 Any difficulties encountered, challenges overcome, and lessons learned from performing the lab

Text…

# 10 Comments/feedback on the lab itself

Text…
