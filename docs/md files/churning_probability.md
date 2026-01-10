# Churn Analysis Summary

## Introduction

This analysis examines customer churn risk based on time since first purchase. Negative time values represent periods before a reference point (e.g., before renewal).

| time_since_first_purchase | has_churned | most_likely_outcome | odds_ratio |
|---------------------------|-------------|---------------------|------------|
| -1.50                     | 0.626       | 1.0                 | 1.677      |
| -1.25                     | 0.605       | 1.0                 | 1.535      |
| -1.00                     | 0.584       | 1.0                 | 1.404      |
| -0.75                     | 0.562       | 1.0                 | 1.285      |
| -0.50                     | 0.540       | 1.0                 | 1.176      |

## Key Finding
**All customers in early tenure are predicted to churn** (`most_likely_outcome = 1.0`), with churn probability ranging from 54% to 62.6%.

## How to Convert Odds Ratio to Percentage (Step by Step)

### Step 1: Understand the Formula
```
odds_ratio = probability / (1 - probability)
```

### Step 2: Rearrange to Solve for Probability
```
probability = odds_ratio / (1 + odds_ratio)
```

### Step 3: Calculate for Each Value

**Example 1: odds_ratio = 1.677**
```
1.677 / (1 + 1.677) = 1.677 / 2.677 = 0.626 = 62.6%
```

**Example 2: odds_ratio = 1.535**
```
1.535 / (1 + 1.535) = 1.535 / 2.535 = 0.605 = 60.5%
```

**Example 3: odds_ratio = 1.404**
```
1.404 / (1 + 1.404) = 1.404 / 2.404 = 0.584 = 58.4%
```

**Example 4: odds_ratio = 1.285**
```
1.285 / (1 + 1.285) = 1.285 / 2.285 = 0.562 = 56.2%
```

**Example 5: odds_ratio = 1.176**
```
1.176 / (1 + 1.176) = 1.176 / 2.176 = 0.540 = 54.0%
```

## Quick Reference Table
| odds_ratio | calculation | percentage | matches has_churned? |
|------------|-------------|------------|---------------------|
| 1.677      | 1.677/2.677 | 62.6%      | ✓ (0.626)           |
| 1.535      | 1.535/2.535 | 60.5%      | ✓ (0.605)           |
| 1.404      | 1.404/2.404 | 58.4%      | ✓ (0.584)           |
| 1.285      | 1.285/2.285 | 56.2%      | ✓ (0.562)           |
| 1.176      | 1.176/2.176 | 54.0%      | ✓ (0.540)           |

## Business Insight
Customers have **highest churn risk (62.6%) soon after first purchase**, with risk decreasing slightly over time but remaining above 50%. This indicates **early customer experience issues** needing immediate attention.

## Recommended Action
**Focus retention efforts on first 1.5 time units post-purchase** when odds ratio is highest (1.677 = 62.6% churn probability).