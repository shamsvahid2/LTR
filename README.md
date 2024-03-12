# Learning to Rank Task:
This repository is dedicated to developing a Learning to Rank (LTR) model aimed at enhancing the relevance of search results in a given dataset.

## How to Run:
To execute this project and replicate the results, please follow these steps:
1. Begin by installing the necessary dependencies listed in `requirements.txt` using the command `pip install -r requirements.txt`.
2. Proceed by running the `EDA_feature-selection.ipynb` notebook, which utilizes the primary datasets to perform exploratory data analysis and feature selection. This notebook will generate a preprocessed dataset and save it as `cleaned_data.csv`.
3. Lastly, open and execute the `ML_model.ipynb` notebook for hyperparameter tuning of the machine learning model and to evaluate its performance on the test dataset.

## EDA and Feature Selection Notebook Overview:
This notebook covers a comprehensive workflow designed to prepare and enhance the dataset for the Learning to Rank task. Key stages include:

1. **Categorical Value Handling**: We address high-cardinality categorical variables through frequency encoding, reducing feature space complexity (comparing to one hot) while preserving informative patterns.

2. **Feature Augmentation**: New features are derived from existing data to enrich the model's input, including rankings and ratios that capture underlying trends and relationships.

3. **Integrating Product Information into Queries**: Product attributes are integrated into query data, emphasizing temporal aspects like mean and standard deviation of product interactions over time to capture dynamic user behavior.

4. **Exploratory Data Analysis (EDA)**:
   - **4.1 Correlation Analysis**: We identify relationships between variables to inform feature selection and mitigate multicollinearity.
   - **4.2 Missing Value Analysis**: Strategies are employed to handle missing data, considering the proportion of missingness and its impact on analysis.
   - **4.3 Histograms & Boxplots**: These visualizations aid in understanding distributional characteristics and identifying outliers.
   - **4.4 Outlier Detection**: We apply methods like Isolation Forest to detect and address outliers, ensuring the robustness of our model.

5. **Feature Selection**: Utilizing insights from EDA, we employ techniques to identify and retain the most informative features, enhancing model performance and efficiency.

For detailed explanations and methodologies, please refer to the markdowns within the notebook.

## Machine Learning Model Overview:
In this notebook, we leverage XGBRanker, to tackle our ranking problem. The process unfolds as follows:

1. **Train-Test Split**: We partition the data into training and testing sets with an 80-20 split, ensuring that all instances of a given `q_id` remain together to prevent data leakage and maintain the integrity of our evaluation.

2. **Cross-Validation and Hyperparameter Tuning**: Through cross-validation, we systematically explore various hyperparameter configurations to identify the set that yields the best performance, ensuring our model is finely tuned for the task.

3. **Model Evaluation**: Upon finalizing our model, we evaluate its performance on the unseen test data. The model demonstrates its effectiveness with an impressive NDCG score of 0.926.

For detailed explanations and methodologies, please refer to the markdowns within the notebook.
