# **Kickstarter Success Prediction**

This project explores the **Kickstarter KickstarterScrape Dataset** and builds machine-learning models to predict whether a campaign will be **successful** based on project characteristics.

## **Team Members**
| Name             | GitHub Handle | Contribution                                                             |
|------------------|---------------|--------------------------------------------------------------------------|
| Ishveen Kaur    | @ishveenk9 |             |
| Amaima Awais   | @AAwais-12     |   |
| Gracious Ogyiri Asare     | @sheisgracious  |                  |
| Lize Chen      | @lc430       |   |


**Challenge Advisor:** Parth Rana (State Street)

## 🎯 **Project Highlights**

- Developed multiple machine learning models (Random Forest, Logistic Regression, Neural Network, KNN) to predict Kickstarter campaign success with about **84.5% accuracy**.
- Achieved **F1 score of 0.84** and **ROC AUC of 0.91**, demonstrating strong predictions for both successful and failed campaigns.
- Generated actionable insights to inform business decisions at for Kickstarter campaigns, identifying key success factors.
- Implemented comprehensive data preprocessing including Winsorization for outlier treatment, one-hot encoding for categorical features, and addressed data leakage by removing post-campaign features.

### **View Streamlit Application:** https://kickstarter-success-predictor.streamlit.app/
---

## 👩🏽‍💻 **Setup and Installation**

**Prerequisites:**
- Python 3.11 or higher
- Jupyter Notebook
- DSI_kickstarterscrape_dataset.csv file

- **Step-by-step instructions:**

1. **Clone the repository:**
```bash
   git clone https://github.com/lc430/bttai-fall-ai-studio-project-repo.git
   cd bttai-fall-ai-studio-project-repo
```

2. **Install dependencies:**
```bash
   pip install jupyter nbformat pandas numpy matplotlib seaborn scipy scikit-learn
```

3. **Access the dataset:**
   - Ensure `DSI_kickstarterscrape_dataset.csv` is in the `data/` folder
   - Encoding: ISO-8859-1

4. **Run the notebooks:**
   - Start with `data_prep.ipynb` to preprocess the data 
   - Then run the model notebook:
     - `RF.ipynb` - Random Forest (Best performing model)
     - `LR.ipynb` - Logistic Regression
     - `NN.ipynb` - Neural Network (MLP)
     - `KNN.ipynb` - K-Nearest Neighbors


## **Project Overview**
This project was completed as part of the Break Through Tech AI Studio program, Fall 2025. The AI Studio program provides students with hands-on experience working on real-world machine learning challenges presented by the industry partners.

The goal of this project is to:
- Clean and preprocess a real Kickstarter dataset  
- Engineer meaningful features (e.g., project state, funded month)  
- Handle missing values & outliers  
- Apply one-hot encoding to categorical features  
- Train and evaluate ML models, including:
  - **K-Nearest Neighbors**
  - **Logistic Regression**
  - **Neural Networks**
- Conduct exploratory data analysis (EDA)

**Real-World Significance:**
Kickstarter campaigns are critical funding strategies for creative projects, startups, innovative ideas, etc. However, **only about 37% of campaigns succeed**. Understanding what drives this success could:
- Help entrepreneurs optimize their campaigns before launch
- Provide platforms with tools to support campaign creators
- Reduce wasted effort and resources on campaigns likely to fail

The potential impact includes:
- Getting data-driven guidance on setting realistic goals and campaign parameters
- Early identification of campaigns with high success probability

---

## 📊 **Data Exploration**

**Dataset Overview:**
- **File:** `DSI_kickstarterscrape_dataset.csv`  
- **Format:** CSV file with ISO-8859-1 encoding
- **Initial Size:** 45,957 projects × 17 features
- **Final Size:** 38,504 projects × 119 features (after preprocessing)
- **Geographic Scope:** United States only (filtered by location)
  
**Key Features Used:**
- `goal`  
- `pledged`  
- `funded percentage`  
- `backers`  
- `duration`  
- `category`, `subcategory`  
- `location`  
- `funded date`

--

## 🧠 **Model Development**
### 1. Random Forest (Best Performing)
- **Baseline Model:** default parameters - 83.9% accuracy
- **Hyperparameter Tuning:**
  - Grid Search with 5-fold cross-validation
  - Total combinations: 216 models tested
  - **Best Parameters:** `n_estimators=200`, `max_depth=None`, `min_samples_split=10`, `min_samples_leaf=1`, `max_features='sqrt'`
- **Final Performance:** 84.5% accuracy, F1=0.84

### 2. Logistic Regression
- **Performance:** 82.7% accuracy, F1=0.84, ROC AUC=0.91
- **Strengths:** Strong precision (85%) and recall (82%); excellent probability calibration

### 3. Neural Network 
- **Baseline Performance:** 81.9% accuracy, F1≈0.82
- **Hyperparameter Tuning:**
  - **Best Parameters:** `hidden_layer_sizes=(50,)`, `alpha=0.0001`, `learning_rate_init=0.01`
- **Final Performance:** 83.7% accuracy, F1=0.82

### 4. K-Nearest Neighbors
- **Baseline:** Default KNN- 69.1% accuracy
- **Hyperparameter Tuning:**
  - **Best Parameters:** `n_neighbors=25`, `weights='distance'`, `p=1` (Manhattan distance)
- **Final Performance:** 71.2% accuracy, F1=0.71

---

## 📈 **Results & Key Findings**
**Model Performance Summary:**

| Model | Accuracy | Precision | Recall | F1 Score | ROC AUC | Notes |
|-------|----------|-----------|--------|----------|---------|-------|
| **Random Forest** | **84.5%** | **0.84** | **0.84** | **0.84** | - | Best overall; captures non-linear patterns |
| **Logistic Regression** | 83.1% | 86.7% | 0.82 | 0.84 | **0.91** | Excellent probability  |
| **Neural Network** | 82.3% | 0.82 | 0.82 | 0.82 | - | Good performance, simpler architecture  |
| **K-Nearest Neighbors** | 0.71 | 0.71 | 0.71 | 0.71 | - | Lower performance; complex decision boundaries |

**Detailed Random Forest Results (Best Model):**
```
Confusion Matrix:
                Predicted Failed    Predicted Success
Actual Failed        3,569              842
Actual Success         707            4,508
```

---
## 🚀 **Next Steps**
   - API development for integration with campaign planning tools
   - Implement fairness constraints during training
   - Implementing interpretable results for the website

## 📝 **License**

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 **Acknowledgements**

We would like to express our sincere gratitude to:
- **Break Through Tech AI Program and Staff** for providing this opportunity to work on a real-world machine learning challenge alonside technical mentorship and networking
- **Parth Rana**, our Challenge Advisor, for involvement, industry expertise, and feedback throughout the project lifecycle
- Our Teaching Assistant, Vasu for his guidance and support through out the project
