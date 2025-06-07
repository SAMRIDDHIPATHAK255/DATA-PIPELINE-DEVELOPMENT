# DATA-PIPELINE-DEVELOPMENT

*COMPANY: CODTECH IT SOLUTIONS

*NAME*: SAMRIDDHI PATHAK

*INTERN ID*: CT08DL700

*DOMAIN*: DATA SCIENCE

*DURATION*: 8 WEEKS

*MENTOR*: NEELA SANTOSH

This project presents a comprehensive machine learning pipeline built to predict passenger survival outcomes from the Titanic disaster using the well-known Titanic dataset. The goal of this model is to classify whether a passenger survived based on features such as age, fare paid, gender, and port of embarkation. The pipeline is implemented using Python with the help of several powerful libraries from the scikit-learn ecosystem. It demonstrates a clean and modular approach to machine learning that includes preprocessing of both numerical and categorical data, training of a classification model, evaluating its performance, and saving the trained model for future use.

The dataset used (titanic_sample.csv) is assumed to have been preprocessed minimally and contains a mix of numeric and categorical features. The target variable is survived, which indicates whether a passenger lived (1) or died (0). The input features used for training the model are age, fare, sex, and embarked. Since machine learning models in scikit-learn generally do not accept categorical variables in their raw string format, preprocessing is essential. This is where the power of ColumnTransformer is utilized. It allows separate preprocessing pipelines for different feature types: numerical and categorical.

For numerical features like age and fare, a StandardScaler is applied. This scaler standardizes the features by removing the mean and scaling to unit variance, which is important for many machine learning algorithms to perform optimally. For categorical features like sex and embarked, a OneHotEncoder is used. This transforms each categorical column into multiple binary columns, each representing a unique category. The encoder is set to handle_unknown='ignore' to gracefully deal with unforeseen categories during inference.

The ColumnTransformer is embedded within a scikit-learn Pipeline, which is a highly recommended practice. This pipeline includes both the preprocessing steps and the model itself—in this case, a RandomForestClassifier. A Random Forest is an ensemble learning method that builds multiple decision trees during training and outputs the class that is the majority vote among the individual trees. It is known for being robust, easy to use, and capable of handling both numerical and categorical data (once encoded).

Once the pipeline is defined, the dataset is split into training and testing sets using train_test_split. This allows the model to be evaluated on unseen data to estimate its performance in real-world scenarios. The model is trained using the training set and evaluated using the test set. Predictions are generated for the test data, and the model’s accuracy is calculated using accuracy_score, which provides a simple yet informative performance metric.

Finally, the entire pipeline—including preprocessing steps and the trained classifier—is saved to a file named model.pkl using joblib. This step is crucial for deploying the model into production. By saving the pipeline as a single object, it can later be loaded and used to make predictions on new data without needing to reapply any of the preprocessing manually. This greatly simplifies future use and ensures consistency between training and inference environments.

In summary, this project not only builds a predictive model for Titanic survival but also demonstrates best practices in machine learning engineering: modular pipelines, proper preprocessing, model evaluation, and serialization. It serves as a strong foundation for deploying real-world classification systems where data must be transformed, predictions made, and performance measured in a repeatable and scalable way.


