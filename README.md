# **Drug Safety Analysis**

A statistical and visual analysis of the safety of a new drug compared to a placebo, focusing on adverse effects and the role of age in treatment outcomes.

## **Objective**
The purpose of this project is to:
- Evaluate the occurrence of adverse effects between the Drug and Placebo groups.
- Examine if the number of adverse effects is independent of the treatment and control groups.
- Analyze whether age influences the treatment outcomes.

## **Dataset**
- **Source**: A randomized controlled trial dataset provided for analysis.
- **Features**:
  - **`trx`**: Treatment group (Drug or Placebo).
  - **`adverse_effects`**: Binary indicator for at least one adverse effect (Yes/No).
  - **`num_effects`**: Count of adverse effects experienced by a participant.
  - **`age`**: Participant's age.
  - Additional demographic and biological markers such as `sex`, `wbc` (white blood cell count), and `rbc` (red blood cell count).

## **Key Findings**

### **1. Proportion of Adverse Effects (Z-Test)**
- **Test**: Assesses if the proportion of participants reporting adverse effects differs between the Drug and Placebo groups.
- **Result**:
  - **P-value**: **`0.9639`**.
  - **Conclusion**: No significant difference in proportions (\(p > 0.05\)).

### **2. Independence of Number of Adverse Effects (Chi-Square Test)**
- **Test**: Evaluates whether the number of adverse effects is independent of the treatment group.
- **Result**:
  - **P-value**: **`0.6150`**.
  - **Conclusion**: The number of adverse effects is independent of treatment group (\(p > 0.05\)).

### **3. Age Differences Between Groups**
- **Normality Test**:
  - Shapiro-Wilk test results indicate that age data is **not normally distributed** for both groups:
    - **Drug Group**: \(W = 0.9768, p = 2.19 \times 10^{-38}\)
    - **Placebo Group**: \(W = 0.9756, p = 2.22 \times 10^{-29}\)
  - **Conclusion**: Non-parametric tests are appropriate for age analysis.
- **Mann-Whitney U Test**:
  - **P-value**: **`0.2569`**.
  - **Conclusion**: No significant difference in age distributions between the Drug and Placebo groups (\(p > 0.05\)).

## **Visualizations**

### **1. Age Distribution by Treatment Group**
This histogram visualizes the age distribution of participants across the Drug and Placebo groups. Key observations include:
- Both groups have a similar age distribution, with most participants aged between **50 and 75 years**.
- The Drug group has a consistently higher participant count due to the 2:1 ratio in the dataset.

<img src="https://github.com/user-attachments/assets/101ecb13-2cac-46d1-bd4c-1db2fc98ddbc" alt="Age Distribution by Treatment Group" width="600">

### **2. Adverse Effects by Age Group**
This bar chart visualizes the count of participants with and without adverse effects (`Yes`/`No`) across different age groups:

- **Key Observations**:
  1. **Participants Without Adverse Effects**:
     - The majority of participants in all age groups did not experience adverse effects.
     - Older age groups (51–65 and 65+) have the highest number of participants without adverse effects.
  2. **Participants With Adverse Effects**:
     - Adverse effects are more commonly observed in older age groups (51–65 and 65+).
     - Younger age groups (0–18, 19–35) show minimal adverse effects, indicating lower susceptibility.
  3. **Conclusion**:
     - Age appears to be a significant factor in adverse effects, with older participants being more susceptible.

<img src="https://github.com/user-attachments/assets/f73c8ce7-3dcf-46d1-8277-9830ca6e91f8" alt="Adverse Effects by Age Group" width="600">


### **3. Number of Adverse Effects by Treatment Group**
This boxplot visualizes the distribution of the number of adverse effects experienced by participants across the Drug and Placebo groups:

- **Key Observations**:
  1. The majority of participants in both groups did not experience any adverse effects (clustered at `0`).
  2. Few participants reported experiencing one or more adverse effects, as shown by outliers at higher counts (`1`, `2`, `3`).
  3. The distribution of adverse effects is almost identical between the Drug and Placebo groups, suggesting no significant difference in the number of adverse effects.

- **Conclusion**:
  - The number of adverse effects appears to be independent of the treatment group, supported by the Chi-Square test (\(p = 0.6150\)).

<img src="https://github.com/user-attachments/assets/bce7b3b8-d619-41d9-b307-29f624a0d6df" alt="Number of Adverse Effects by Treatment Group" width="600">


## **Tools and Methods**
- **Programming Languages**: Python
- **Libraries**: 
  - Data Manipulation: `pandas`, `NumPy`
  - Statistical Analysis: `statsmodels`, `pingouin`
  - Visualization: `Seaborn`, `Matplotlib`
- **Statistical Tests**:
  - Proportion Z-Test
  - Chi-Square Test for Independence
  - Mann-Whitney U Test
 
## **Conclusion**
- The treatment (Drug) is as safe as the Placebo, with no significant increase in adverse effects.
- Age plays a significant role in adverse effects, with older participants being more susceptible.



