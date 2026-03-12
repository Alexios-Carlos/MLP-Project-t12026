📘 Machine Learning Practice Project – Comment Category Prediction
📂 Repository

MLP-Project-t12026

This repository contains the implementation of my Machine Learning Practice Project (MLP) for the IIT Madras BS Degree in Data Science and Applications. The objective of this project is to build machine learning models capable of automatically classifying online comments into predefined moderation categories.

The project combines Natural Language Processing (NLP) techniques with tabular feature engineering to extract meaningful patterns from user-generated text and associated metadata.

🎯 Project Objective

Online platforms receive a large volume of user comments every day. Moderating these comments manually can be challenging and time-consuming. The goal of this project is to develop a machine learning system that can automatically predict the category assigned to each comment by a moderation system.

The task is formulated as a multi-class classification problem, where each comment must be classified into one of four possible categories.

The project explores several machine learning techniques and evaluates their effectiveness in predicting comment categories using both textual and metadata features.

📊 Dataset Description

The dataset used in this project consists of user comments along with metadata features that describe various aspects of the comment.

Main Components of the Dataset
Feature	Description
comment	Raw text content of the user comment
created_date	Timestamp when the comment was posted
post_id	Identifier linking the comment to a discussion thread
emoticon_1, emoticon_2, emoticon_3	Indicators representing presence of emoticons
upvote / downvote	Number of reactions received
race, religion, gender, disability	Indicators of detected identity references
if_1, if_2	Internal system features
label	Target variable representing moderation category

The dataset contains 198,000 training samples and several feature types including:

Textual data

Numerical features

Categorical variables

Boolean indicators

🔍 Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to understand the structure and characteristics of the dataset.

Key observations include:

The dataset contains four target classes representing different comment moderation categories.

The class distribution is imbalanced, with Label 0 being the dominant class (~58%).

Several categorical columns such as race, religion, and gender contain a large number of missing values.

Comment lengths vary widely, indicating that both short and long comments are present.

Visualization techniques were used to explore:

Class distribution

Comment length distribution

Reaction statistics (upvotes and downvotes)

These insights guided the design of preprocessing and modeling strategies.

⚙️ Data Preprocessing

Data preprocessing plays a critical role in preparing the dataset for machine learning models. Several preprocessing steps were implemented.

Text Cleaning

The comment text was normalized by:

Converting all text to lowercase

Removing URLs

Removing special characters and punctuation

Removing extra whitespace

This process reduces noise and standardizes textual inputs.

Handling Missing Values

Missing values were handled appropriately depending on the feature type:

Text features were replaced with empty strings.

Categorical features were encoded while treating missing values as a separate category.

Feature Engineering

Additional metadata features were created to capture meaningful patterns:

Comment length

Word count

Vote difference (upvote - downvote)

Total emoticons

Ratio of capital letters

These engineered features help capture behavioral and contextual information that may influence moderation decisions.

🧠 Feature Representation

The textual content of comments was converted into numerical features using TF-IDF vectorization.

Two types of TF-IDF representations were used:

Word-Level TF-IDF

Captures semantic meaning by analyzing word frequencies.

Character-Level TF-IDF

Captures spelling patterns and subtle textual signals that may indicate abusive or harmful language.

The final feature representation combines:

Text Features (TF-IDF)
+
Engineered Metadata Features

This hybrid representation allows models to learn from both language and behavioral signals.

🤖 Machine Learning Models

Three different machine learning models were trained and compared.

1️⃣ Logistic Regression

Logistic Regression serves as a strong linear baseline model for high-dimensional text data.

Advantages:

Efficient training

Works well with sparse TF-IDF features

Interpretable coefficients

2️⃣ Multinomial Naive Bayes

Naive Bayes is a probabilistic classifier widely used for text classification tasks.

Advantages:

Extremely fast

Performs well with bag-of-words features

Strong baseline for NLP problems

However, it assumes feature independence, which can limit performance.

3️⃣ LightGBM (Final Model)

LightGBM is a gradient boosting algorithm that builds an ensemble of decision trees.

Advantages:

Handles large feature spaces efficiently

Captures nonlinear interactions between features

Works well with mixed feature types

LightGBM demonstrated the best performance among all models tested.

📈 Model Evaluation

Model performance was evaluated using Macro F1-score rather than accuracy.

Why Macro F1?

Because the dataset is imbalanced, accuracy could be misleading.
Macro F1-score treats each class equally and provides a more reliable evaluation.

Model	Macro F1 Score
Logistic Regression	~0.66
Multinomial Naive Bayes	~0.55
LightGBM	~0.80

LightGBM significantly outperformed the baseline models.

🏆 Final Model Performance

The final LightGBM model was trained on the full training dataset and used to generate predictions for the Kaggle competition.

Kaggle Leaderboard Score:
⭐ 0.82155

This score successfully exceeded the project cutoff requirement of 0.80, making the submission eligible for viva evaluation.

🛠 Technologies Used

The project was implemented using the following tools and libraries:

Python

Pandas

NumPy

Scikit-learn

LightGBM

Matplotlib

Seaborn

SciPy

The experiments were conducted using Kaggle Notebooks.

📁 Repository Structure
MLP-Project-t12026/
│
├── FinalNotebook.ipynb
├── README.md
└── submission files
🎓 Learning Outcomes

Through this project, the following machine learning concepts were explored:

Text preprocessing and normalization

Feature engineering for tabular data

TF-IDF vectorization

Model comparison and evaluation

Handling imbalanced datasets

Gradient boosting models

Practical machine learning workflows

🙌 Acknowledgements

This project was completed as part of the Machine Learning Practice Project course in the IIT Madras BS Degree in Data Science and Applications program.

👨‍💻 Author

Muhammad Bilal
IIT Madras BS Degree – Data Science
Machine Learning Practice Project (t12026)
