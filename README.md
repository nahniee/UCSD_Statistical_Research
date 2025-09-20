# Statistical Research Project Overview

This repository contains **two independent statistical research projects**:  
**Research 1 – Bayesian Credible Intervals & Sequential Trials**  
**Research 2 – Lottery Modeling & Nonparametric Regression Analysis**

---

## Research 1: Bayesian Inference and Sequential Analysis

### Project Overview

This project applies **Bayesian methods** to infer the success probability \(p\) in a binomial experiment.  
It further incorporates the concept of **sequential trials**, where the experiment can be stopped early once sufficient statistical confidence is achieved.

### Highlights

- Uses a **Beta-Binomial model** to compute posterior distributions  
- Calculates **95% Highest Posterior Density (HPD)** credible intervals  
- Defines a **Bayesian stopping rule** based on HPD width ≤ 0.03  
- Visualizes the **decision boundary** where a trial should stop or continue  

### Key Outcomes

- Developed a simulation-based method for computing the HPD interval  
- Constructed a clear decision boundary in the (Successes, Failures) space  
- Confirmed that extreme values of \(\hat{p}\) require fewer samples, while values near 0.5 require more — validating intuitive understanding of uncertainty  

---

## Research 2: Lottery Simulation & Nonparametric Modeling

This project consists of two parts:

---

### Lottery Simulation: No-Winner Probability

- A weekly lottery sells \(T\) tickets with numbers from 000–999  
- Tickets are picked from a **non-uniform distribution**:  
  \( p_n \propto \frac{1}{(n+1)^{1.5}} \)  
- The goal is to calculate the **probability that no one wins**, and find the \(T^\star\) such that this probability ≈ 0.50  

**Insight**: Even with a large number of tickets sold, the non-uniform selection means there’s still a significant chance of no winner.

---

### Nonparametric Regression on Crash Test Data

#### Part A: Regressogram & LOWESS

- Applied **nonparametric smoothing** (Regressogram and LOWESS) to model head acceleration during a motorcycle crash  
- Estimated prediction risk using:  
  - Covariance Penalty (Mallows' \(C_p\))  
  - Bootstrap Optimism  
  - 7-Fold Cross-Validation  

* Results showed agreement among risk estimation methods and led to an **optimal smoothing parameter** selection  
* LOWESS yielded smooth and flexible fits, especially in noisy regions  

---

#### Part B: Adaptive Regressogram

- Built a **recursive, adaptive-width regressogram** using greedy RSS minimization  
- Penalized model complexity using:

  \[
  \text{Risk}(k) = \frac{\text{RSS}(k)}{n} + \frac{2 \hat{\sigma}^2 k \log(k)}{n}
  \]

* Produced models that adapt to **local structure** in the data  
* Compared with standard histogram-based risk minimization for validation  

---

## Summary Table

| Project       | Topic                       | Technique                        | Key Results                                          |
|---------------|-----------------------------|----------------------------------|------------------------------------------------------|
| Research 1     | Bayesian Sequential Trial    | HPD Interval, Beta-Binomial      | Computed decision boundary for early stopping        |
| Research 2-1   | Lottery Simulation           | Non-uniform sampling, Bisection  | Estimated tickets needed for 50% no-winner probability |
| Research 2-2   | Nonparametric Regression     | LOWESS, CV, Bootstrap            | Identified optimal smoothness for crash data trend   |
| Research 2-3   | Adaptive Regressogram        | Recursive RSS splits, Penalized Risk | Built interpretable models with complexity control |

---