---
layout: post
title: "Is It Alice or Bella? A Bayesian Approach to Eavesdropping 101"
date: 2024-10-31
categories: probability bayesian-inference
---

# Is It Alice or Bella? A Bayesian Approach to Eavesdropping 101

Sally is new to the area and overhears her friends talking about another female friend. She knows they’re talking about either **Alice** or **Bella** but doesn’t know which. Here’s a breakdown of how we can use some probability to help Sally figure it out!

## Problem Breakdown

1. **Define Events:**
   - \( A \): The friends are talking about **Alice**.
   - \( B \): The friends are talking about **Bella**.
   - \( C \): The person being discussed drives a **white car**.
   - \( S \): The person being discussed **hates sushi**.

2. **Given Information:**
   - Sally is **90% certain** that Alice has a white car: \( P(C|A) = 0.9 \).
   - Sally knows **nothing about Bella's car**, so assuming maximum uncertainty, \( P(C|B) = 0.5 \) (we assume an equal chance that Bella’s car could be white or black).
   - Sally is **90% certain** that Bella likes sushi: \( P(\text{likes sushi}|B) = 0.9 \), so the probability that Bella **hates sushi** is \( P(S|B) = 0.1 \).
   - Sally knows **nothing about Alice’s preference for sushi**, so assuming maximum uncertainty, \( P(S|A) = 0.5 \).

3. **Goal:**
   We want to find \( P(A | C \cap S) \), the probability that the friends are talking about Alice given that the person they are discussing drives a white car and hates sushi.

## Step-by-Step Solution

### Step 1: Calculate \( P(C \cap S | A) \) and \( P(C \cap S | B) \)

- For **Alice**:
  \[
  P(C \cap S | A) = P(C | A) \cdot P(S | A) = 0.9 \times 0.5 = 0.45
  \]

- For **Bella**:
  \[
  P(C \cap S | B) = P(C | B) \cdot P(S | B) = 0.5 \times 0.1 = 0.05
  \]

### Step 2: Define Prior Probabilities

Assuming **maximum uncertainty** in the absence of any other information about who they might be talking about, we assume equal priors:
\[
P(A) = 0.5 \quad \text{and} \quad P(B) = 0.5
\]

### Step 3: Calculate \( P(C \cap S) \) (Total Probability)

Using the law of total probability:
\[
P(C \cap S) = P(C \cap S | A) \cdot P(A) + P(C \cap S | B) \cdot P(B)
\]
Substitute the values:
\[
P(C \cap S) = (0.45 \times 0.5) + (0.05 \times 0.5) = 0.225 + 0.025 = 0.25
\]

### Step 4: Apply Bayes’ Theorem to Find \( P(A | C \cap S) \)

\[
P(A | C \cap S) = \frac{P(C \cap S | A) \cdot P(A)}{P(C \cap S)}
\]
Substitute the values:
\[
P(A | C \cap S) = \frac{0.45 \times 0.5}{0.25} = \frac{0.225}{0.25} = 0.9
\]

## Conclusion

The probability that the friends are talking about **Alice** is \( \mathbf{0.9} \), or **90%**.
