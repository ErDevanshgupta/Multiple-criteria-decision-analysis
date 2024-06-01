# TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution)

This repository contains a Python implementation of the TOPSIS (Technique for Order of Preference by Similarity to Ideal Solution) method for Multi-Criteria Decision Making (MCDM).

## Table of Contents

- [Overview](#overview)
- [Detailed Explanation](#detailed-explanation)
  - [Steps Involved in TOPSIS](#steps-involved-in-topsis)
- [Implementation](#implementation)
- [Usage](#usage)
  - [Prerequisites](#prerequisites)
  - [Explanation](#explanation)

## Overview

TOPSIS is a widely used technique for solving MCDM problems. It compares a set of alternatives by calculating the geometric distance from an ideal solution and a negative ideal solution. The alternative that is closest to the ideal solution and farthest from the negative ideal solution is considered the best.

## Detailed Explanation

### Steps Involved in TOPSIS

1. **Construct the Decision Matrix**: 
    - List all the alternatives and criteria.
    - Create a matrix where rows represent alternatives and columns represent criteria.

2. **Normalize the Decision Matrix**: 
    - Normalize the decision matrix to make the criteria comparable. This is done using the formula:
      \[
      r_{ij} = \frac{x_{ij}}{\sqrt{\sum_{k=1}^{m} x_{kj}^2}}
      \]
      where \( x_{ij} \) is the value of the \(i\)-th alternative for the \(j\)-th criterion.

3. **Calculate the Weighted Normalized Decision Matrix**:
    - Multiply the normalized decision matrix by the criteria weights:
      \[
      v_{ij} = w_j \cdot r_{ij}
      \]
      where \( w_j \) is the weight of the \(j\)-th criterion.

4. **Determine the Ideal and Negative Ideal Solutions**:
    - The ideal solution consists of the best values for each criterion:
      \[
      A^+ = \left\{ \left( \max v_{ij} \ \text{for}\ j \in J \right), \left( \min v_{ij} \ \text{for}\ j \in J' \right) \right\}
      \]
      where \(J\) is the set of benefit criteria and \(J'\) is the set of cost criteria.
    - The negative ideal solution consists of the worst values for each criterion:
      \[
      A^- = \left\{ \left( \min v_{ij} \ \text{for}\ j \in J \right), \left( \max v_{ij} \ \text{for}\ j \in J' \right) \right\}
      \]

5. **Calculate the Separation Measures**:
    - Calculate the separation distance of each alternative from the ideal and negative ideal solutions:
      \[
      S_i^+ = \sqrt{\sum_{j=1}^{n} (v_{ij} - A_j^+)^2}
      \]
      \[
      S_i^- = \sqrt{\sum_{j=1}^{n} (v_{ij} - A_j^-)^2}
      \]

6. **Calculate the Relative Closeness to the Ideal Solution**:
    - The relative closeness of the \(i\)-th alternative to the ideal solution is given by:
      \[
      C_i^* = \frac{S_i^-}{S_i^+ + S_i^-}
      \]

7. **Rank the Alternatives**:
    - Rank the alternatives based on the closeness coefficient \( C_i^* \). The alternative with the highest closeness coefficient is considered the best.

## Implementation

The implementation involves the following steps:
1. **Define the Decision Matrix**: A matrix containing the alternatives and their corresponding criteria values.
2. **Define Criteria Weights**: A weight vector representing the importance of each criterion.
3. **Normalize the Decision Matrix**: Normalize the decision matrix to make the criteria comparable.
4. **Calculate the Weighted Normalized Matrix**: Multiply the normalized decision matrix by the criteria weights.
5. **Determine Ideal and Negative Ideal Solutions**: Identify the best and worst values for each criterion.
6. **Calculate the Separation Distances**: Compute the Euclidean distances from each alternative to the ideal and negative ideal solutions.
7. **Calculate the Closeness Coefficients**: Determine the relative closeness of each alternative to the ideal solution.
8. **Determine the Best Alternative**: Identify the alternative with the highest closeness coefficient.

## Usage

### Prerequisites

- Python 3.10.1
- NumPy



### Explanation

- **Decision Matrix**: A matrix where each row represents an alternative and each column represents a criterion.
- **Weights**: A vector containing the weight of each criterion.
- **Normalized Decision Matrix**: Each element of the decision matrix is divided by the square root of the sum of squares of its column.
- **Weighted Normalized Matrix**: Each element of the normalized decision matrix is multiplied by the corresponding weight.
- **Ideal Solution**: The best value for each criterion.
- **Negative Ideal Solution**: The worst value for each criterion.
- **Euclidean Distances**: The distances of each alternative from the ideal and negative ideal solutions.
- **Closeness Coefficients**: The relative closeness of each alternative to the ideal solution.
- **Best Alternative**: The alternative with the highest closeness coefficient.
