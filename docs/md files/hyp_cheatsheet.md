
# 📘 **Expanded Hypothesis Testing Cheat Sheet (Theory + Practice)**


## **1. Identify the Population Parameter**

This step defines *what exactly you are testing*. Every hypothesis test focuses on one unknown population value.

### **What it means (Theory)**

A population parameter is the true value in the entire population, such as:

* Mean delivery time (μ)
* Proportion of late shipments (p)
* Difference between two group means (μ₁ − μ₂)
* Variance of a process (σ²)

You cannot measure the population directly, so you take a sample.

### **Why it matters (Practical Use)**

This choice determines:

* which test you use
* which formula you apply
* which Python function you call

**Example:**
Testing whether late shipment rate is > 6% → population parameter is **proportion p**.


## **2. State the Null and Alternative Hypotheses**

These are the competing claims you will test.

### **What it means (Theory)**

* **Null hypothesis (H₀):** The default assumption. No change, no effect, no difference.
* **Alternative hypothesis (H₁):** What you want to show. A difference or direction.

They are always statements about the **population parameter** identified in Step 1.

### **Why it matters (Practical Use)**

Hypotheses guide:

* one-tailed vs two-tailed test
* how Python calculates the p-value
* your final decision

**Example:**
H₀: p = 0.06
H₁: p > 0.06

You are checking if the late shipments exceed 6%.


## **3. Choose the Test Statistic and the Null Distribution**

A test statistic standardizes your sample so you can compare it to a known distribution.

### **What it means (Theory)**

Different situations require different statistics:

#### **z-score**

Used when sample size is large or population SD is known.

#### **t-score**

Used when sample size is small and population SD is unknown.

#### **χ² (chi-square)**

Used for categorical counts and testing independence.

#### **F-statistic**

Used for comparing variances and group differences in ANOVA.

Each statistic has its own distribution (z, t, chi-square, F) with known probability behavior.

### **Why it matters (Practical Use)**

Choosing the wrong test statistic produces incorrect conclusions.

**Python Examples:**

```python
stats.ttest_1samp()    # t-test
stats.proportions_ztest()   # z-test for proportion
stats.chi2_contingency()    # chi-square test
stats.f_oneway()            # F-test (ANOVA)
```


## **4. Measure Evidence Against the Null Hypothesis**

After computing the test statistic, you compare its result to what is expected if H₀ is true.

### **What it means (Theory)**

* You transform your observed difference (sample mean or proportion) into a standardized number: **z, t, χ², or F**
* Then you calculate the **p-value**, which tells you:

  > “If the null hypothesis is true, how likely is it to observe this sample result?”

### **Why it matters (Practical Use)**

The p-value determines your decision.

**Rules:**

* If **p ≤ α** → reject H₀ (evidence of effect)
* If **p > α** → fail to reject H₀ (no strong evidence)

Common α = 0.05.

**Python Example:**

```python
stat, p = stats.ttest_1samp(data, 6)
print(p)
```


## **5. Conduct the Hypothesis Test in Python**

Now you run the statistical test programmatically.

### **What it means (Theory)**

The Python function:

* calculates the test statistic
* finds the p-value
* uses the correct distribution

### **Why it matters (Practical Use)**

Python automates the math and reduces mistakes.
Engineers rely on libraries like SciPy, NumPy, Statsmodels.

**Examples by test type:**

**1-sample t-test**

```python
stats.ttest_1samp(sample, popmean=50)
```

**Proportion test**

```python
stats.proportions_ztest(count, nobs, value=0.06)
```

**Chi-square**

```python
stats.chi2_contingency(table)
```

**ANOVA**

```python
stats.f_oneway(group1, group2, group3)
```


## **6. Interpret Results in Context**

You translate the statistical decision into a real-world conclusion.

### **What it means (Theory)**

Statistics gives numerical evidence, but the final answer must relate back to the business or scientific question.

### **Why it matters (Practical Use)**

Without context, the test has no meaning.

**Example interpretation:**
“The p-value is 0.012, which is below 0.05. This means there is strong evidence that the late shipment rate is greater than 6%.”

Interpretation should:

* be clear
* answer the question
* avoid statistical jargon when possible


# 📌 **Quick Summary Table (Theory + Practice)**

| Step               | Theory                      | Practical Use                |
| ------------------ | --------------------------- | ---------------------------- |
| Identify parameter | Focus on μ, p, or σ²        | Helps choose the test        |
| State hypotheses   | Define H₀ and H₁            | Sets direction of test       |
| Choose statistic   | Select z, t, χ², F          | Selects Python function      |
| Measure evidence   | Compute statistic + p-value | Apply α = 0.05 decision rule |
| Run in Python      | Use SciPy/statsmodels       | Automates math               |
| Interpret          | Connect to problem          | Make real-world decision     |


