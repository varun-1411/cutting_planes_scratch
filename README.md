# :dart: Generalized Assignment Problem (GAP) with LP Relaxation and Cutting Planes

## Overview
This project aims to improve the **Linear Programming (LP) relaxation bounds** for the **Generalized Assignment Problem (GAP)** by incorporating cutting-plane methods. The focus is on minimizing the objective function while adding cuts such as:

- **Gomory Cuts** from the simplex tableau
- **Knapsack Cover Cuts** (solved via separation problems)
- **Lifted Cuts** generated from the above procedures

The project implements these methods, reports results across multiple instances, and highlights performance improvements achieved.

---

## Objective
The Generalized Assignment Problem (GAP) is a well-known combinatorial optimization problem. The goal is to minimize a linear objective function subject to assignment and capacity constraints. In this project:

- Solve GAP instances as LP relaxations.
- Use **cutting-plane techniques** to strengthen LP bounds.
- Report results based on the objective values and execution time.

---

## Data
The input datasets for GAP instances are located in the `GAP` folder. These datasets are sourced from the OR-Library:

- [GAP Instance Description](http://people.brunel.ac.uk/~mastjjb/jeb/orlib/gapinfo.html)
- File format: `.lp` (Linear Programming formulation)

---

## Approach
1. **Solve Initial LP Relaxation:** Start with GAP instances provided as LP files.
2. **Add Cutting Planes:**
   - **Gomory Cuts:** Derived from the simplex tableau to strengthen LP bounds.
   - **Knapsack Cover Cuts:** Solved via separation problems.
   - **Lifted Cuts:** Extend and enhance the generated cuts for further improvement.
3. **Terminate Execution:** The solution process terminates after 120 seconds or when an integer solution is found.
4. **Performance Reporting:** For each instance, report the following:
   - Initial LP relaxation value
   - Final LP relaxation value after cuts
   - Execution time (seconds)
   - Whether an integer solution was found

---

## Results

### Knapsack Cover Cuts
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

### Gomory Cuts
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

---

## Features
- Solves LP relaxation for GAP instances.
- Implements Gomory cuts and Knapsack cover cuts to improve bounds.
- Reports both intermediate and final objective values.
- Terminates execution based on a time threshold (120s) or integer solution.
- Simple and modular implementation for ease of extension.

---

## Setup

### Prerequisites
- Python 3.8+
- Gurobi Optimizer (Academic License or higher)
- LP file parser (Gurobi's `Model.read()`)

### Installation
Ensure you have Gurobi installed and properly configured:
```bash
pip install gurobipy


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





