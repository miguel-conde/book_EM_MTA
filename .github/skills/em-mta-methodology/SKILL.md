---
name: em-mta-methodology
description: "Expert knowledge in Expectation-Maximization algorithms for Multi-Touch Attribution, Marketing Mix Models, and applied Bayesian inference in marketing analytics. Use when discussing EM algorithms, MTA methodology, MMM attribution, latent variable models, or marketing attribution problems."
---

# EM/MTA Methodology Expertise

## Core Concepts

### Expectation-Maximization for Attribution
- **E-step**: Compute expected latent allocations $z_{b,h}$ under current parameters
- **M-step**: Update productivity parameters $\lambda_h$ using allocation weights
- **Mass conservation**: Ensure $\sum_h z_{b,h} = y_b$ (total incremental impact)
- **Convergence**: Monitor likelihood changes and parameter stability

### Key Notation
- $\omega_{b,h}$: Exposure for entity $h$ in brick $b$ (adstocked/saturated)
- $\lambda_h$: Productivity parameter for entity $h$
- $z_{b,h}$: Latent contribution of entity $h$ to brick $b$
- $y_b$: Total MMM incremental impact for brick $b$

## Attribution Framework

### MMM → MTA Methodology
1. **Top-down approach**: Start with MMM channel totals
2. **Exposure design**: Transform raw impressions (adstock + saturation)
3. **Allocation model**: Use EM to distribute MMM totals across entities
4. **Validation**: Ensure allocations sum to MMM incrementality

### Common Challenges
- **Identifiability**: Collinear exposures → arbitrary parameter splits
- **Cold start**: New entities with minimal exposure history
- **Stability**: Model performance across data updates
- **Causality confusion**: Attribution ≠ causal impact measurement

## Business Communication

### Stakeholder Messaging
- **CMOs**: "Preserves MMM incrementality while providing campaign-level insights"
- **Data Scientists**: "Probabilistic allocation using EM with mass conservation constraints"
- **Finance**: "Allocates exact MMM totals—no attribution inflation"
- **Legal**: "Correlation-based allocation, not causal claims about individual touchpoints"

### HCP-Brick Analogy
Explain complex methodology using familiar healthcare concepts:
- **HCP** (Healthcare Provider) → **Entity** (campaign/creative)
- **Brick** (geographic territory) → **Time/geo unit**
- **Total prescriptions** → **MMM incremental contribution**
- **Doctor visits** → **Media exposure/opportunity**

## Problem-Solution Patterns

### When to Apply
**Input signals that trigger this skill:**
- "How to allocate channel impact to campaigns?"
- "EM algorithm convergence issues"
- "MTA vs MMM causality questions"
- "Attribution methodology selection"
- "Mass conservation in attribution"

### Solution Templates

**For identifiability issues:**
```
Problem: Identical exposure patterns → arbitrary allocations
Solutions: 
1. Hierarchical priors with partial pooling
2. Regularization (L1/L2) on productivity parameters
3. External constraints from incrementality tests
```

**For cold start entities:**
```
Problem: New campaigns with limited history
Solutions:
1. Bayesian hierarchical model with category priors
2. Shrinkage toward category/channel means
3. Bootstrap from similar historical entities
```

**For convergence problems:**
```
Problem: EM not converging or oscillating
Solutions:
1. Check exposure collinearity (condition number)
2. Add small regularization term
3. Verify mass conservation constraints
4. Monitor likelihood and parameter changes
```