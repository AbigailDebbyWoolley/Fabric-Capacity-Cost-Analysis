# **Microsoft Fabric Cost Calculation (F64 SKU)**

## **Overview**
This document outlines the methodology for calculating the cost of running workloads in **Microsoft Fabric** under the **F64 SKU** tier. The pricing model is based on **Capacity Units (CUs)** and the region being used.

## **Background**
This cost analysis is conducted to help **Brock Group** optimize resource allocation and budget planning for Microsoft Fabric workloads. Stakeholders require a detailed breakdown to understand cost variations based on different execution frequencies and ensure that workloads are running efficiently without unnecessary expenses.

## **Cost Calculation Approach**
The cost for Microsoft Fabric is determined based on the **selected SKU tier**, the **hourly rate per Capacity Unit (CU)**, and the **frequency of execution**. The updated cost estimation formula considers different execution schedules.

### **Key Formula**
For each execution run:

\[
\text{Cost per Run} = \text{Capacity Units Used per Run} \times \text{Hourly Rate per CU}
\]

The total cost for different periods is calculated based on the number of runs.

## **Three Cost Calculation Models**
We have implemented three distinct cost models to analyze the execution runs:

### **1. Standard Daily Runs (4 Runs per Day)**
- The system executes **4 runs per day** consistently.
- The total cost is calculated for **daily, monthly, and yearly usage**.

#### **Final Formula**
\[
\text{Total Monthly Cost} = 4 \times 24 \times 30 \times \text{Hourly Rate per CU}
\]
\[
\text{Total Yearly Cost} = 4 \times 24 \times 365 \times \text{Hourly Rate per CU}
\]

### **2. Hourly Runs Daily (24 Runs per Day)**
- The system executes **1 run per hour**, leading to **24 runs per day**.
- The total cost reflects the increased frequency of execution.

#### **Final Formula**
\[
\text{Total Monthly Cost} = 24 \times 24 \times 30 \times \text{Hourly Rate per CU}
\]
\[
\text{Total Yearly Cost} = 24 \times 24 \times 365 \times \text{Hourly Rate per CU}
\]

### **3. Hybrid Runs (4 Runs Daily & Hourly Runs for Month-End Period)**
- The system executes **4 runs per day** normally.
- During the **last 7 days of each month**, the execution frequency increases to **hourly runs (24 runs per day)**.
- The cost estimation accounts for this hybrid execution pattern.

#### **Final Formula**
For the first **23 days** of the month:
\[
\text{Cost}_{\text{standard}} = 4 \times 24 \times 23 \times \text{Hourly Rate per CU}
\]

For the last **7 days** of the month:
\[
\text{Cost}_{\text{month-end}} = 24 \times 24 \times 7 \times \text{Hourly Rate per CU}
\]

Total Monthly Cost:
\[
\text{Total Monthly Cost} = \text{Cost}_{\text{standard}} + \text{Cost}_{\text{month-end}}
\]

Total Yearly Cost:
\[
\text{Total Yearly Cost} = 12 \times \text{Total Monthly Cost}
\]

## **Reference Documentation**
For the latest pricing and detailed information, refer to the official Microsoft Fabric pricing documentation:

- [Microsoft Fabric Pricing](https://azure.microsoft.com/en-us/pricing/details/microsoft-fabric/)
- [Microsoft Fabric Capacity Units](https://learn.microsoft.com/en-us/fabric/capacity-units)

This document will be updated as Microsoft releases new pricing updates or modifies its cost structure.
