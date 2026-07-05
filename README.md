# Parameter Estimation for Parametric Curve Reconstruction

## Overview

This project aims to estimate the unknown parameters of a parametric curve using the given set of (x, y) points. The parameters to be estimated are:
- θ (Theta)
- M
- X

The problem can be viewed as an inverse parameter estimation task, where the curve equation is known but its parameters are hidden. The objective is to find the parameter values that generate a curve closest to the given data points by minimizing the L1 distance.

## Parametric Equations (Given data)

x = t cos(θ) − e^(M|t|) × sin(0.3t) × sin(θ) + X

y = 42 + t sin(θ) + e^(M|t|) × sin(0.3t) × cos(θ)

Parameter ranges:

- 0° < θ < 50°
- -0.05 < M < 0.05
- 0 < X < 100
- 6 < t < 60

## Approach

The following steps were followed to estimate the unknown parameters:

1. Read and visualize the given dataset.
2. Implement the given parametric equations in Python.
3. Generate curves using different combinations of θ, M and X.
4. Compare each generated curve with the original data using the L1 distance.
5. Record the parameter combination with the minimum error.
6. Repeat the search with smaller step sizes around the best result to obtain a better estimate.
7. Plot the final reconstructed curve for comparison.


## Methodology

### Step 1 – Data Understanding
The given dataset was loaded using Pandas and visualized using Matplotlib to understand the overall shape of the curve.

### Step 2 – Curve Generation
The given mathematical equations were implemented as a Python function that generates the curve for any valid values of θ, M and X.

### Step 3 – Error Calculation
The difference between the generated curve and the given curve was measured using the L1 distance.

A smaller L1 distance indicates a better match between the generated and actual curves.

### Step 4 – Parameter Search
A brute-force search was performed by testing different values of θ, M and X within the given ranges.
After obtaining the best result, the search was repeated around those values using smaller step sizes to improve the parameter estimation.

### Step 5 – Final Comparison
Using the final estimated parameters, the curve was generated again and compared with the original data.

## Challenges Faced

- Understanding the effect of each parameter on the curve.
- Choosing suitable parameter ranges and step sizes.
- Finding parameter values that minimize the L1 distance.

## Future Work

The current implementation uses a brute-force search to estimate the unknown parameters.
In future work, the search process can be improved by using more efficient parameter estimation techniques to reduce computation time while maintaining or improving the accuracy.

## Conclusion

This project demonstrates a brute-force approach for estimating the unknown parameters of a parametric curve using the given data points.

The problem was solved in a step-by-step manner by first searching the entire parameter range and then repeating the search with smaller step sizes around the best result. This helped improve the parameter estimation while keeping the approach simple and systematic.

Although the brute-force method requires more computation time, it provides a clear and straightforward way to estimate the unknown parameters and reconstruct the given curve.
