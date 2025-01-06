
# **Optimal Portfolio Allocation using CRRA Utility Function**

This project provides a Python implementation for determining the **optimal portfolio allocation** across four asset classes (**Equity**, **Fixed Income**, **Gold**, and **Real Estate**) using the **Constant Relative Risk Aversion (CRRA)** utility function. The code simulates terminal wealth over a 10-year horizon using **Geometric Brownian Motion (GBM)** and computes the expected utility for different random portfolio allocations. The portfolio with the highest expected utility is selected as the optimal allocation.

---

## **How It Works**

1. **Asset Classes**:  
   The code considers four asset classes:
   - Equity
   - Fixed Income
   - Gold
   - Real Estate

2. **Parameters**:
   - **Mean Returns**: The expected annual return for each asset class.
   - **Volatilities**: The annual standard deviation (volatility) for each asset class.
   - **Correlation Matrix**: Defines how the returns of different asset classes are correlated.
   - **CRRA Coefficient, $\gamma$**: The degree of risk aversion. A value of $\gamma$ = 0.9 indicates mild risk tolerance.

3. **Simulation**:
   - The code generates **10,000 random portfolio allocations** using the Dirichlet distribution (ensuring that all weights sum to 1).
   - For each allocation, it simulates the terminal wealth after 10 years using **Geometric Brownian Motion**.
   - The CRRA utility for each simulation is computed, and the expected utility for each portfolio allocation is determined.

4. **Optimal Portfolio**:
   - The code identifies the portfolio allocation that maximizes the expected utility.
   - The optimal allocation is displayed in both text format and a **pie chart**.

---

## **Usage**

1. **Pre-requisites**:
   - Python 3.x
   - `numpy`
   - `matplotlib`

2. **Running the Code**:
   - Copy the Python code into a Jupyter Notebook or a Python script.
   - Install the required libraries using:
     ```bash
     pip install numpy matplotlib
     ```
   - Run the code to see the optimal portfolio allocation and a pie chart of the results.

---

## **Key Sections of the Code**

1. **Parameter Definition**:
   - `mean_returns`: Expected annual returns for each asset class.
   - `volatilities`: Annual volatilities (risks) of the asset classes.
   - `correlation_matrix`: Correlations between the asset classes.
   - `gamma`: CRRA coefficient representing the investor's risk aversion.

2. **Simulation of Terminal Wealth**:
   - Terminal wealth is simulated using **Geometric Brownian Motion** to model the uncertainty in asset returns over time.

3. **Utility Calculation**:
   - The **CRRA utility function** is used to compute the utility of simulated terminal wealth:

     $$U(W) = 
        \begin{cases} 
        \frac{W^{1 - \gamma}}{1 - \gamma}, & \text{if } \gamma \neq 1 \\
        \ln(W), & \text{if } \gamma = 1
        \end{cases}
    $$

   - The expected utility is computed by averaging the utility across all simulations.

4. **Optimal Allocation**:
   - The code identifies the allocation with the highest expected utility and displays it as a pie chart.

---

## **Example Output**

### **Optimal Allocation (Gamma = 0.9)**

```text
Optimal Allocation:
Equity: 62.25%
Fixed Income: 0.11%
Gold: 0.65%
Real Estate: 37.00%
```

### **Pie Chart**

The optimal allocation is also displayed in a pie chart, showing the percentage allocation for each asset class.

---

## **Customization**

You can modify the following parameters to fit your specific use case:

1. **Investment Horizon** (`n_years`):  
   Change the number of years over which terminal wealth is simulated.
   
2. **Number of Allocations** (`n_allocations`):  
   Increase or decrease the number of random portfolio allocations tested.

3. **Risk Aversion Coefficient** (`gamma`):  
   Adjust the CRRA coefficient to reflect different levels of risk aversion:
   - $\gamma$ < 1 : Risk-tolerant or risk-loving investor.
   - $\gamma$ = 1 : Logarithmic utility, representing a risk-neutral investor.
   - $\gamma$ > 1 : Risk-averse investor.

---

## **References**

1. **Constant Relative Risk Aversion (CRRA)**:  
   CRRA is a widely used utility function in economics and finance to model investor preferences under uncertainty.

2. **Geometric Brownian Motion (GBM)**:  
   GBM is a stochastic process commonly used in financial modeling to simulate asset prices over time.

---

## **License**

This code is provided under the **MIT License**. You are free to use, modify, and distribute it.

---
