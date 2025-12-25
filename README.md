# Life Insurance Pricing Model

This project demonstrates an actuarial life insurance pricing model built in Python. It replicates the core structure and thinking behind professional insurance pricing models while using a simplistic approach in calculating the premiums. 

The model calculates policy premiums such that the expected profit margin meets a target level, using numerical solving techniques and actuarial-style cashflow projections.

## Model Overview

The model prices policies based on:

- Entry Age
- Policy Term
- Target Profit Margin
- Premium (solved variable)

### Key actuarial components
- Survival & Inforce Projection  
- Deaths & Claims  
- Premium cash inflows  
- Acquisition & renewal expenses    
- Discounting of cashflows  

Then it calculates:

$$
\text{Profit Margin} 
= \frac{ \text{PV(Premiums)} - \text{PV(Claims)} - \text{PV(Expenses)} }
{ \text{PV(Premiums)} }
$$

## Methodology & Techniques

| Component | Approach |
|---------|---------|
Mortality | Simple increasing qₓ curve  
Lapses | Declining lapse rate model  
Cashflows | Annual projected values  
Discounting | Deterministic discount factor  
Profit Targeting | Root solving 
Performance | Parallel computation via Joblib  
Output | Premium Table (Age × Term)  

## Data Pipeline

- Generate mortality table  
- Generate lapse assumptions  
- Build annual cashflow projection  
- Compute PV of Premiums, Claims, and Expenses
- Compute actual profit margin  
- Use numerical solver to find premium meeting target margin  
- Repeat across all ages & terms  
- Export premium table

## Output

The model produces a premium rate table:

| Age | Policy Term | Premium |
|-----|-------------|--------|
| 25  | 10    | ₹X |
| 25  | 11    | ₹Y |
| …   | …           | … |
| 50  | 30          | ₹Z|

## Sharing The Output

The generated table is exported to Excel and saved in a local directory.

## Technologies Used

- Python
- Pandas
- Numpy
- Scipy
- Joblib

## Author
**Shitikshu Vyas**
