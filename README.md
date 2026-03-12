# 📘 Machine Learning Practice Project – Comment Category Prediction

## 📂 Repository
**MLP-Project-t12026**

This repository contains the implementation of my **Machine Learning Practice Project (MLP)** for the **IIT Madras BS Degree in Data Science and Applications**. The objective of this project is to build machine learning models capable of automatically classifying online comments into predefined moderation categories.

The project combines **Natural Language Processing (NLP)** techniques with **tabular feature engineering** to extract meaningful patterns from user-generated text and associated metadata.

---

# 🎯 Project Objective

Online platforms receive a large volume of user comments every day. Moderating these comments manually can be challenging and time-consuming. The goal of this project is to develop a machine learning system that can **automatically predict the category assigned to each comment by a moderation system**.

The task is formulated as a **multi-class classification problem**, where each comment must be classified into one of four possible categories.

The project explores several machine learning techniques and evaluates their effectiveness in predicting comment categories using both textual and metadata features.

---

# 📊 Dataset Description

The dataset used in this project consists of **user comments along with metadata features** that describe various aspects of the comment.

### Main Components of the Dataset

| Feature | Description |
|------|-------------|
| comment | Raw text content of the user comment |
| created_date | Timestamp when the comment was posted |
| post_id | Identifier linking the comment to a discussion thread |
| emoticon_1 | Indicator of emoticon type 1 |
| emoticon_2 | Indicator of emoticon type 2 |
| emoticon_3 | Indicator of emoticon type 3 |
| upvote | Number of positive reactions |
| downvote | Number of negative reactions |
| race | Indicator of detected race-related reference |
| religion | Indicator of detected religion-related reference |
| gender | Indicator of detected gender-related reference |
| disability | Indicator of disability reference |
| if_1, if_2 | Internal moderation signals |
| label | Target variable representing moderation category |

The dataset contains **198,000 training samples** and multiple feature types including:

- Textual data
- Numerical features
- Categorical features
- Boolean features

---

# 🔍 Exploratory Data Analysis (EDA)

Exploratory Data Analysis was conducted to better understand the dataset structure and identify potential patterns.

Key insights from the analysis include:

- The dataset contains **four moderation categories**.
- The class distribution is **imbalanced**, with **Label 0 forming the majority (~58%)**.
- Several categorical columns such as **race, religion, and gender contain missing values**.
- Comment lengths vary significantly across the dataset.

Visualization techniques were used to analyze:

- Class distribution
- Comment length distribution
- Reaction statistics (upvotes and downvotes)

These insights guided the feature engineering and modeling approach.

---

# ⚙️ Data Preprocessing

Data preprocessing was performed to ensure the dataset was suitable for machine learning models.

### Text Cleaning

The comment text was normalized using the following steps:

- Convert text to lowercase
- Remove URLs
- Remove punctuation and special characters
- Remove extra whitespace

This process standardizes textual inputs and reduces noise.

---

### Handling Missing Values

Different strategies were applied based on feature types:

- Missing comments were replaced with empty strings.
- Missing categorical values were encoded appropriately.

---

### Feature Engineering

Several additional features were created to capture useful patterns:

- **Comment length**
- **Word count**
- **Vote difference** (`upvote - downvote`)
- **Total emoticons**
- **Capital letter count**

These features provide additional behavioral signals that may influence moderation decisions.

---

# 🧠 Feature Representation

Text data was converted into numerical features using **TF-IDF vectorization**.

Two types of TF-IDF representations were used:

### Word-Level TF-IDF
Captures semantic information from the comment text.

### Character-Level TF-IDF
Captures character patterns and spelling variations that may indicate abusive language.

The final feature space combines:


This hybrid representation enables models to learn from both language patterns and user interaction signals.

---

# 🤖 Machine Learning Models

Three different machine learning algorithms were implemented and compared.

## 1️⃣ Logistic Regression

Logistic Regression serves as a strong baseline for high-dimensional text data.

**Advantages**

- Fast training
- Works well with sparse TF-IDF matrices
- Interpretable model

---

## 2️⃣ Multinomial Naive Bayes

Naive Bayes is a probabilistic classifier commonly used for text classification tasks.

**Advantages**

- Extremely fast
- Performs well on bag-of-words features
- Simple yet effective baseline

However, the independence assumption between features may limit performance.

---

## 3️⃣ LightGBM (Final Model)

LightGBM is a gradient boosting algorithm based on decision trees.

**Advantages**

- Efficient handling of large feature spaces
- Captures nonlinear relationships
- High predictive performance

LightGBM achieved the best results among all models tested.

---

# 📈 Model Evaluation

Model performance was evaluated using **Macro F1-score**.

### Why Macro F1?

Because the dataset is imbalanced, accuracy alone would not be reliable.  
Macro F1-score evaluates each class equally and provides a balanced performance metric.

| Model | Macro F1 Score |
|------|---------------|
| Logistic Regression | ~0.66 |
| Multinomial Naive Bayes | ~0.55 |
| LightGBM | ~0.80 |

LightGBM significantly outperformed the baseline models.

---

# 🏆 Final Model Performance

The final LightGBM model was trained on the entire training dataset and used to generate predictions for the Kaggle competition.

**Kaggle Leaderboard Score**

⭐ **0.82155**

This score successfully exceeds the required cutoff score of **0.80**, making the project eligible for the viva evaluation stage.

---

# 🛠 Technologies Used

The project was implemented using the following tools and libraries:

- **Python**
- **Pandas**
- **NumPy**
- **Scikit-learn**
- **LightGBM**
- **Matplotlib**
- **Seaborn**
- **SciPy**

All experiments were conducted using **Kaggle Notebooks**.

---

# 📁 Repository Structure
MLP-Project-t12026/
│
├── notebooks/
│ └── FinalNotebook.ipynb
│
├── submissions/
│ └── final_submission.csv
│
├── README.md
└── LICENSE

---

# 🎓 Learning Outcomes

This project provided practical experience in several important machine learning concepts:

- Text preprocessing and normalization
- Feature engineering for tabular data
- TF-IDF feature extraction
- Model comparison and evaluation
- Handling imbalanced datasets
- Gradient boosting algorithms
- Building complete machine learning pipelines

---

# 🙌 Acknowledgements

This project was completed as part of the **Machine Learning Practice Project course** in the **IIT Madras BS Degree in Data Science and Applications** program.

---

# 👨‍💻 Author

**Muhammad Bilal**  
IIT Madras BS Degree – Data Science  
Machine Learning Practice Project (t12026)





