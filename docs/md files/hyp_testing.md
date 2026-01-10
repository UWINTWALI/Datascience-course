**core terminologies used in hypothesis testing**

## **1. Null Hypothesis (H₀)**

**Meaning:** The default assumption—nothing has changed, no effect, no difference.
**What it measures:** It gives you a baseline to compare your sample against.


## **2. Alternative Hypothesis (H₁ or Ha)**

**Meaning:** Opposite of H₀. It states that there *is* an effect or difference.
**What it measures:** The direction you want to prove (greater than, less than, or different).


## **3. Significance Level (α)**

**Meaning:** The acceptable risk of making a wrong decision. Usually 0.05.
**What it measures:** The probability of rejecting H₀ when it is actually true (Type I error).


## **4. Test Statistic (z-score, t-score, χ², F-statistic)**

**Meaning:** A value your code calculates to show how far your sample is from the null assumption.
**What it measures:** The standardized distance between observed data and what H₀ expects.



## **i. z-score**

A **z-score** measures how far your sample mean or proportion is from the population value, expressed in units of standard deviation. It assumes the population standard deviation is known or the sample size is large (n > 30). In simple terms, it tells you how unusual your sample is if the null hypothesis is true. The larger the absolute z-value, the stronger the evidence against the null.


## **ii. t-score**

A **t-score** works like a z-score but is used when the sample size is small (n < 30) or when the population standard deviation is unknown. It accounts for extra uncertainty by using the sample standard deviation instead. The t-distribution has heavier tails, meaning it allows more variation in small samples. A higher absolute t-value indicates stronger evidence against the null hypothesis.


## **iii. χ² (Chi-square statistic)**

The **chi-square statistic** measures how much difference exists between observed frequencies and expected frequencies. It is used mainly for categorical data, especially in tests of independence (e.g., relationship between gender and product preference) or tests of goodness-of-fit. A larger chi-square value means the observed distribution differs strongly from what the null hypothesis predicts.


## **iv. F-statistic**

The **F-statistic** compares the variance between groups to the variance within groups. It is used in ANOVA and regression model comparison. If the variance between groups is much larger than the variance inside each group, the F-value becomes large, suggesting that at least one group mean is different from the others. A high F-statistic provides evidence against the null hypothesis of equal means.



## **5. p-Value**

**Meaning:** Probability of observing your data *if H₀ was true*.
**What it measures:** How strong your evidence is against H₀.
Lower p-value → stronger evidence → reject H₀.


## **6. Critical Value**

**Meaning:** A cutoff value based on α (like ±1.96 for 95% confidence).
**What it measures:** The threshold your test statistic must exceed to reject H₀.


## **7. Confidence Interval (CI)**

**Meaning:** A range of values likely to contain the true population parameter.
**What it measures:** The estimation accuracy of your sample.


## **8. Type I Error**

**Meaning:** Rejecting a true H₀ (false positive).
**What it measures:** How often your test falsely signals an effect.


## **9. Type II Error**

**Meaning:** Failing to reject a false H₀ (false negative).
**What it measures:** How often your test misses a real effect.


## **10. Power of a Test**

**Meaning:** The ability to detect a true effect.
**What it measures:** Probability of correctly rejecting a false H₀.

## **11. Sample Statistic (p̂, x̄)**

**Meaning:** What you calculated from your sample—mean, proportion, variance.
**What it measures:** The observed evidence used in the test.


## **12. Population Parameter (μ, p, σ)**

**Meaning:** The true value you are trying to learn about.
**What it measures:** The unknown quantity you test hypotheses about.


## **13. One-tailed Test**

**Meaning:** Tests for an effect in *one* direction (greater or less).
**What it measures:** Directional change.


## **14. Two-tailed Test**

**Meaning:** Tests for any difference (both directions).
**What it measures:** Any deviation from H₀.
---
---
---

**Correct sequence** for the steps in hypothesis testing

# ✅ **Correct Order**

1. **Identify population parameter that is hypothesized about**
2. **Specify the null and alternative hypotheses**
3. **Determine (standardized) test statistic and corresponding null distribution**
4. **Measure evidence against the null hypothesis and compare to significance level**
5. **Conduct hypothesis test in Python**
6. **Interpret the results in the context of the original problem**


# ✅ **Reasons for Each Step (Clear & Logical)**

### **1. Identify population parameter that is hypothesized about**

You must first know *what* you are testing: a mean, a proportion, a difference, or a variance. It gives direction to the whole test.


### **2. Specify the null and alternative hypotheses**

Once you know the parameter, you define the competing statements (H₀ and H₁). These guide the rest of the statistical procedure.


### **3. Determine the test statistic and the null distribution**

Based on your data type and sample size, you choose whether to use a z-score, t-score, χ², or F-statistic. This step standardizes your data for comparison.


### **4. Measure evidence against the null and compare to significance level**

You calculate the p-value from the test statistic and compare it to α (like 0.05). This shows whether the evidence is strong enough to reject H₀.


### **5. Conduct hypothesis test in Python**

After understanding the theory, you run the statistical test using Python libraries like SciPy or statsmodels. This automates calculations and gives exact results.


### **6. Interpret the results in the context of the original problem**

Finally, you translate the statistical result into a real-world conclusion (e.g., “Late shipments are significantly higher than 6%”). This ensures your decision has meaning.



