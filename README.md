# A/B Testing Analysis for Cookie Cats Mobile Game
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Polars Badge](https://img.shields.io/badge/Polars-0075FF?logo=polars&logoColor=fff&style=for-the-badge)
![A/B Testing](https://img.shields.io/badge/A\/B_Testing-F6AE2D?style=for-the-badge)

## 🎮 Project Overview

This project presents a complete A/B testing analysis for the popular mobile game, Cookie Cats. The goal is to determine the impact of moving the first mandatory stopping point (a "gate") from level 30 to level 40 on player retention and engagement.

The analysis follows a structured, end-to-end methodology, starting from a formal experiment design and hypothesis formulation, through data cleaning and exploratory analysis, to statistical testing and a final business recommendation.


## 🔗 Quick Links
* 📓 **[Full Code in Jupyter Notebook](ab-test.ipynb)**


## 🧪 What is A/B Testing?
A/B testing is a method for comparing two versions of a product or feature (A and B) to determine which one performs better. Users are randomly split into a **control group** (seeing the original version A) and a **treatment group** (seeing the new version B).

By tracking a key metric for both groups, we can use statistical analysis to confidently determine if the change had a significant impact or if the observed difference was just due to random chance. This process allows businesses to make data-driven decisions and reduce the risk of launching features that negatively affect user experience.


## 🎯 The Business Question

As players progress, they encounter gates that require them to wait or make an in-app purchase. The core business question is:

> Does moving the first gate from level 30 to level 40 lead to higher player retention and engagement?

The underlying hypothesis is that encountering a gate too early might be a frustrating experience, and delaying it could lead to a more committed player base.



## 📁 Dataset

The dataset contains data from 90,189 players who installed the game during the A/B test period.

* **Source:** [Kaggle - Mobile Games A/B Testing](https://www.kaggle.com/datasets/mursideyarkin/mobile-games-ab-testing-cookie-cats/data)
* **Columns:**
    * `userid`: A unique identifier for each player.
    * `version`: The experiment group (`gate_30` or `gate_40`).
    * `sum_gamerounds`: The number of game rounds played in the first week.
    * `retention_1`: Boolean indicating if the player returned 1 day after installation.
    * `retention_7`: Boolean indicating if the player returned 7 days after installation.



## 📋 Analysis Structure

The project is structured into the following key stages:

1.  **Experiment Design**: Formulating hypotheses, defining primary and secondary metrics (KPIs), setting statistical parameters (α=0.01, power=0.90), and selecting appropriate statistical tests.
2.  **Data Cleaning & EDA**: Loading the data, handling a significant outlier, and performing exploratory data analysis to understand the distributions and initial trends.
3.  **Statistical Analysis**: Performing formal hypothesis tests:
    * **Chi-Squared Test** for retention metrics (proportions).
    * **Mann-Whitney U Test** for game rounds (non-parametric distribution comparison).
4.  **Results & Interpretation**: Translating the statistical outputs (p-values) into clear findings.
5.  **Conclusion & Recommendation**: Summarizing the results and providing a final, data-driven business recommendation.



## 💡 Key Findings

The statistical analysis yielded the following key insights:

* **7-Day Retention (Primary Metric)**: There was a **statistically significant decrease** in 7-day retention for the group with the gate at level 40 (p-value = 0.0016). The retention rate dropped from 19.0% to 18.2%.
* **1-Day Retention**: There was no statistically significant difference between the two groups (p-value = 0.0750).
* **Game Rounds Played**: There was no statistically significant difference in the distribution of game rounds played between the two groups (p-value = 0.0509).



## 🚀 Final Recommendation 

The experiment provides strong evidence that moving the gate from level 30 to level 40 is **detrimental to long-term player retention** without providing any measurable benefit to player engagement.

**The final recommendation is to not roll out the change and to maintain the gate at its original position at level 30.**



## 💻 Technologies Used

* **Data Manipulation**: Polars
* **Statistical Analysis**: SciPy
* **Data Visualization**: Seaborn, Matplotlib