# NBA Player Career Longevity Prediction: Naive Bayes Model

#### Google Working Example

An end-to-end Machine Learning project using a **Gaussian Naive Bayes** classifier to predict whether a National Basketball Association (NBA) player's career will last five years or more based on their rookie-season performance statistics.

---

## 📌 Project Overview
Retaining players who can withstand the high-pressure environment of professional basketball and contribute to team success over time is a critical decision for NBA management and coaches. This project builds a predictive classifier to assist front offices in making data-driven roster decisions[cite: 1].

Using historical rookie-season performance data, we model the probability of a player's career longevity ($Career \ge 5\text{ years}$) using a **Gaussian Naive Bayes** algorithm, which is highly suitable for continuous predictor variables[cite: 1].

---

## 📊 Dataset Summary
The dataset contains **1,341 player observations** with performance metrics extracted from their rookie years[cite: 1]:
* **Target Variable (`target_5yrs`)**: Binary/Boolean (1 if career lasted $\ge 5$ years, 0 otherwise)[cite: 1].
* **Predictor Features**[cite: 1]:
    * `fg`: Field goal percentage[cite: 1]
    * `3p`: 3-point field goal percentage[cite: 1]
    * `ft`: Free throw percentage[cite: 1]
    * `reb`: Rebounds per game[cite: 1]
    * `ast`: Assists per game[cite: 1]
    * `stl`: Steals per game[cite: 1]
    * `blk`: Blocks per game[cite: 1]
    * `tov`: Turnovers per game[cite: 1]
    * `total_points`: Total points scored in the rookie season[cite: 1]
    * `efficiency`: Player efficiency rating[cite: 1]

---

## 🛠️ Project Workflow

### 1. Data Preparation & Split
* Separated the target variable (`target_5yrs`) from the performance features[cite: 1].
* Divided the dataset into a **75% training set** (1,005 observations) and a **25% testing set** (335 observations) to validate generalization using `sklearn.model_selection.train_test_split`[cite: 1].

### 2. Model Selection
* **Algorithm**: **Gaussian Naive Bayes (`GaussianNB`)** from `scikit-learn`[cite: 1]. 
* **Justification**: Because the predictor variables are continuous numerical metrics, a Gaussian implementation is chosen, assuming features follow a normal distribution[cite: 1].

### 3. Training & Prediction
* The classifier was fitted on the training subsets (`X_train`, `y_train`)[cite: 1].
* Predictions were generated on the unseen test set (`X_test`)[cite: 1].

---

## 📈 Results & Model Evaluation

The model was evaluated using standard classification metrics[cite: 1]:

| Metric | Score | Interpretation / Insights |
| :--- | :--- | :--- |
| **Accuracy** | **68.96%** | The overall rate of correct predictions across both classes[cite: 1]. |
| **Precision** | **84.06%** | High precision indicates that when the model predicts a player will last $\ge 5$ years, it is correct **84.06%** of the time (minimizing False Positives)[cite: 1]. |
| **Recall** | **58.59%** | Shows weaker performance in capturing all players who will last $\ge 5$ years, indicating a higher rate of False Negatives[cite: 1]. |
| **F1-Score** | **69.05%** | Balances precision and recall to provide a combined metric of overall predictive power[cite: 1]. |

### 🧩 Confusion Matrix Analysis
The confusion matrix highlights how the model manages its classifications[cite: 1]:
* **High True Positive Rate**: The model is exceptionally strong at identifying promising talent (players with long careers)[cite: 1].
* **False Negatives**: The model tends to be conservative, sometimes predicting a short career for players who actually go on to play for five or more years[cite: 1].

---

## 🧠 Key Takeaways
1. **Metric Nuance**: Evaluating the model solely on accuracy (69.0%) would hide its underlying strengths[cite: 1]. The high precision (84.1%) makes it a highly reliable tool for identifying true long-term prospects[cite: 1].
2. **Strategic Deployment**: NBA front offices can use this model as a robust filter to confidently draft or sign players predicted to have long-term careers, knowing that positive predictions are highly reliable[cite: 1].

---

## 💻 Environment & Quick Start

### Prerequisites
Make sure you have Python 3 and the following scientific libraries installed:
```bash
pip install pandas scikit-learn jupyter
```
