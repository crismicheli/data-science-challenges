**Assignment: Build Multi-Target Prediction Models**

**Task Overview:**
In this assignment, each client_id corresponds to a single row that contains both feature values and target labels.

There are multiple target columns, each representing a different prediction task. All targets are binary, but not every target is available for every client. In other words, a client is only labeled for a given target when we explicitly have a 0 or 1 for that column; otherwise, the value is missing and should be treated as “unlabeled.”
You can recognize the target columns by their naming convention: they all end with "_tgt" (for example, high_ltv_tgt).

All remaining columns—everything except client_id and the target columns—should be treated as features. These features are shared across all prediction tasks.

**Dataset Structure:**
- Each row represents one client (identified by `client_id`)
- Multiple binary target columns (ending in `_tgt`, e.g., `high_ltv_tgt`)
- Targets may be missing (null) for some clients—only some clients have been labeled with 0 or 1
- All columns except `client_id` and target columns are features
- For all targets, **1 = "bad" event** (the outcome we want to avoid)

**Requirements:**

1. **Exploratory Data Analysis**
   - Analyze correlations, missing values, and other key patterns in the data

2. **Data Preparation**
   - Transform and prepare the data for predictive modeling

3. **Model Building**
   - Build models that balance predicting both the 1 class (bad events) AND the 0 class (good events)
   - Note: Accuracy alone is not a good metric here—consider class imbalance

4. **Multi-Target Strategy**
   - Explain your approach: Would you use multiple models (one per target) or a single model for all targets?
   - **Goal:** Minimize false negatives (reject all 1's) while accepting all 0's across all targets

5. **Model Validation on Unlabeled Data**
   - How would you evaluate your model's performance on clients where the target is unknown/null?
   - Explain your validation strategy
