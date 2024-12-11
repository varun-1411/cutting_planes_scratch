[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/mhltO2Ep)
# :memo: Assignment 2

## Objective

In this assignment, you are required to improve the LP relaxation bounds of the Generalized Assignment Problem (GAP). Remember to use a min objective.

## Data 
The data on which your models must be run is in the GAP folder.
- GAP [[Description]](http://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html)

## Problems
Solve the original problem as a linear program. You can choose to import your LP files from Assignment 1. You are then allowed to perform the following operations. 
- Add Gomory cuts from simplex tableau
- Add knapsack cover cuts by solving separation problems
- Lift cuts that are generated from the above procedures

Terminate your code after 120 s (or if you found an integer solution) and report the instance and LP value at termination. Upload the codes and the two tables as a PDF. 

## Rules and Dos and Don'ts
- No parallel processing is allowed
- You are allowed to use a preprocessing phase
- The time for your codes must include importing the LP file, preprocessing, and the main code
- The submission with the best LP bound for the most number of instances will be awarded the extra points in Round 2.

# Knapsack cover cuts results

| File         | Initial Objective Value | Final Objective Value  | Time Taken (seconds) | IP Solution Found |
|--------------|-------------------------|------------------------|----------------------|-------------------|
| a05100.lp    | 1697.73                 | 1697.87                | 10.01                | No                |
| a05200.lp    | 3234.74                 | 3235.00                | 0.02                 | Yes               |
| a10100.lp    | 1358.56                 | 1360.00                | 0.10                 | Yes               |
| a10200.lp    | 2623.00                 | 2623.36                | 10.02                | No                |
| a20100.lp    | 1157.08                 | 1158.00                | 0.04                 | Yes               |
| a20200.lp    | 2337.33                 | 2338.53                | 10.03                | No                |
| b05100.lp    | 1831.33                 | 1833.93                | 10.00                | No                |
| b05200.lp    | 3547.41                 | 3547.94                | 10.02                | No                |
| b10100.lp    | 1400.67                 | 1404.00                | 10.01                | No                |
| b10200.lp    | 2815.05                 | 2817.79                | 10.02                | No                |
| b20100.lp    | 1155.18                 | 1162.12                | 10.01                | No                |
| b20200.lp    | 2331.14                 | 2334.64                | 10.04                | No                |


# Gomory's cover cut results

| File              | Initial Objective Value | Final Objective Value  | Time Taken (seconds) | IP Solution Found |
|-------------------|-------------------------|------------------------|----------------------|-------------------|
| a05100.lp         | 1697.73                 | 1698.00                | 2.08                 | Yes               |
| a05200.lp         | 3234.74                 | 3235.00                | 2.34                 | Yes               |
| a10100.lp         | 1358.56                 | 1359.12                | 2.63                 | No                |
| a10200.lp         | 2623.00                 | 2623.00                | 2.25                 | No                |
| a20100.lp         | 1157.08                 | 1158.00                | 1.47                 | No                |
| a20200.lp         | 2337.33                 | 2338.67                | 32.94                | No                |
| b05100.lp         | 1831.33                 | 1833.13                | 1.64                 | No                |
| b05200.lp         | 3547.41                 | 3547.75                | 90.61                | No                |
| b10100.lp         | 1400.67                 | 1403.60                | 15.84                | No                |
| b10200.lp         | 2815.05                 | 2815.95                | 26.89                | No                |
| b20100.lp         | 1155.18                 | 1159.04                | 27.51                | No                |
| b20200.lp         | 2331.14                 | 2332.88                | 113.79               | No                |





