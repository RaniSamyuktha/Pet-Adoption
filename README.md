# Pet-Adoption
HackerEarth Machine Learning challenge :  Adopt a buddy

# Problem statement

Numerous organizations across the world provide shelter to all homeless animals until they are adopted into a new home. However, finding a loving family for them can be a daunting task at times. This International Homeless Animals Day, Hackerearth present a Machine Learning challenge to us: Adopt a buddy.

# Dataset
The dataset consists of parameters such as a unique ID assigned to each animal that is up for adoption, the date on which they arrived at the shelter, their physical attributes such as color, length, and height, among other factors.
The benefits of practicing this problem by using Machine Learning techniques are as follows:
This challenge will help you to actively enhance your knowledge of multi-label classification. It is one of the basic building blocks of Machine Learning
We challenge you to build a predictive model that detects the type and breed of an animal-based on its condition, appearance, and other factors.

The dataset contains information about various pets, including attributes such as:
- **Pet ID**: Unique identifier for each pet
- **Condition**: Physical condition of the pet (e.g., healthy, injured)
- **Color Type**: Color combination of the pet (e.g., black, brown)
- **Breed Category**: Categorical feature indicating the breed type
- **Pet Category**: Categorical feature that classifies pets as different species (e.g., cat, dog)
- **Other attributes**: Possibly containing missing or irrelevant values that need handling.

The dataset is split into training and test sets, with target columns being **Breed Category** and **Pet Category**.

### Data Processing Techniques:
1. **Missing Value Treatment**: There are missing values in columns such as `Condition`. Missing values were handled through conditional imputation based on related columns like `Breed Category` and `Pet Category`.
   
2. **Encoding Categorical Features**: Features like `color_type`, `breed_category`, and `pet_category` are categorical and were transformed into numerical representations using techniques such as **One-Hot Encoding** or **Label Encoding**.

3. **Feature Engineering**: Additional features were likely created or transformed to capture the relationships between categorical variables such as `Color Type`, `Breed Category`, and `Pet Category`.

4. **Train-Test Splitting**: The training data was split further into train and validation sets for model evaluation purposes.

Let's dive deeper into the key areas: **feature engineering** and **modeling**.

### Feature Engineering:
Feature engineering is the process of transforming raw data into features that better represent the underlying problem to the model, resulting in improved model performance. Based on the notebook content, here are some techniques that were likely used:

1. **Handling Missing Values:**
   - The dataset has missing values in the `Condition` column. From the notebook, it seems that missing values were imputed (or filled) based on the relationships with other columns, like `Breed Category` and `Pet Category`.
   - For example, it appears that certain `Breed Category` values, like `2.0`, were correlated with a missing condition in a significant number of instances. Imputing these missing values could be done using the most frequent value, or by calculating a condition score based on other columns.

2. **Encoding Categorical Features:**
   - Categorical features such as `Color Type`, `Breed Category`, and `Pet Category` need to be transformed into numerical formats so that they can be used as input to machine learning models.
   - Techniques like **Label Encoding** (converting each unique category into an integer) or **One-Hot Encoding** (creating binary columns for each category) were likely used for columns like `Color Type` and `Breed Category`.

3. **Interaction Between Variables:**
   - There seems to be a relation between certain features, such as `Breed Category` and `Condition`, as noted from the exploratory analysis. Creating new features that represent these interactions can improve model performance.
   - Example: A new feature could be generated that captures how often a specific breed appears in combination with a specific condition.

4. **Normalization/Scaling:**
   - For certain machine learning algorithms, feature scaling is essential. Although the dataset seems to be mostly categorical, numerical features (if any) would have been scaled using methods like **Min-Max Scaling** or **Standardization** to ensure the features are on the same scale.

---

### Model Selection:

The primary model used is a **Gradient Boosting Classifier** (GBK), a powerful model for tabular data, which uses an ensemble of decision trees. Here's an in-depth look at the model and evaluation techniques:

1. **Gradient Boosting Classifier (GBK):**
   - **Gradient Boosting** is an ensemble technique that builds models sequentially, where each new model corrects the errors of the previous models. It works well for structured/tabular data and is resistant to overfitting when tuned correctly.
   - The Gradient Boosting model used in this notebook likely utilized **decision trees** as base learners and combines them to improve predictive performance.

2. **Training and Validation:**
   - The dataset is split into training and validation sets to avoid overfitting. The training set is used to train the model, while the validation set is used to assess its performance and tune hyperparameters.
   - After training the model on the training data, the model is evaluated on the validation set to calculate performance metrics.

3. **Model Evaluation:**
   - The performance of the model is evaluated using the **F1-score (weighted)**, which is useful when the dataset is imbalanced (i.e., some classes have more samples than others).
   - The notebook reports an F1 score of approximately **90.16%**. This indicates a well-performing model that balances precision and recall for both `Breed Category` and `Pet Category`.

4. **Hyperparameter Tuning:**
   - Gradient Boosting models have several hyperparameters that can be tuned to improve performance, such as:
     - **Learning Rate**: Controls how much each tree contributes to the overall model.
     - **Number of Trees**: More trees generally improve performance but can lead to overfitting.
     - **Max Depth of Trees**: Deeper trees can model more complex relationships but are more prone to overfitting.


### Model Selection:
The following models were explored:
- **Gradient Boosting Classifier** (GBK): A powerful ensemble-based model that combines decision trees to reduce overfitting and achieve higher accuracy. The notebook uses **Gradient Boosting** as the primary model for classification tasks.
  
- **Model Evaluation**: The model was evaluated using the **F1-score** (weighted) to account for class imbalances. The final accuracy score based on the validation set was approximately **90.16%**.


