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

Def-Use per statement:
| Statement| Defined| Used|
|-----|-----|-----|
|1|data, column| |
|2| | data|
|3| total| | 
|4| rowCount| data|
|5| r| rowcount, r|
|6| n| data, r, column|
|7| | n| 
|8| total | n|
|9|
|10| 
|11| r2| rowCount, r2|
|12| n| data, r2, column|
|13| | n|
|14| total | n|
|15| | | 
|16| | | 
|17| | total|

Def-Use Pairs by Variable:
| Variable | Pairs |
|----- | ----- |
| data | (1,2), (1,4), (1,6), (1,12) | 
| column | (1,6), (1,12)|
| total| (3,17), (8,17), (14,17) |
|rowCount|(4,5), (4,11) |
|r|(5,6)|
|n| (6,7), (6,8), (12,13), (12,14) |
|r2| (11,12)| 

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
