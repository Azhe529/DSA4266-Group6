
# DSA4266 Group Project

## Introduction
This project presents a machine learning approach to help distinguish between legitimate and phishing websites and aims to address the limitations of traditional rule-based detection methods. 

As attackers increasingly adopt sophisticated techniques, phishing continues to be a pervasive cybersecurity threat, with recent surges highlighting the inadequacy of traditional detection techniques. Traditional rule-based detection methods are often inadequate against ever-evolving techniques. Machine learning offers a more adaptive, real-time solution to this issue by effectively identifying phishing patterns. Leveraging a balanced dataset of 11,430 URLs and 87 features—including URL structure, webpage content attributes, and external service indicators—we employed a range of classification algorithms, from simpler models like Logistic Regression to more complex approaches such as Multi-layer Perceptron (MLP). 

Our findings indicate that tree-based boosting models, particularly LightGBM, achieved superior performance compared to other models. Further feature analysis reveals that external service indicators play a critical role in distinguishing legitimate from phishing sites, enhancing both model interpretability and practical applicability. This project demonstrates the potential of machine learning in phishing detection and provides a foundation for developing adaptive, robust cybersecurity systems.

## Dataset
### Raw Data
The [dataset](https://doi.org/10.17632/c2gw7fy2j4.3) used in this project is contributed by Abdelhakim Hannousse and Salima Yahiouche. The dataset comprises 11,430 URLs, balanced between legitimate and phishing. It includes 87 features, categorised into three main classes: 56 features extracted from the structure and syntax of the URLs, 24 features derived from the content of corresponding pages, and 7 features obtained through external service queries. In addition to the dataset, Python scripts for feature extraction are provided, allowing for replication or extension in future research. 

The raw data can be found in `/data` folder.

### Preprocessed Datasets

The preprocessed dataset underwent data cleaning and feature engineering to prepare it for model training. Key preprocessing techniques included:

- Feature Selection: ANOVA (Analysis of Variance) was used to identify and retain the most impactful features, improving model performance and reducing dimensionality.

- Word Embedding: URLs were tokenized and embedded using FastText.

- Dimensionality Reduction: An autoencoder was applied to further reduce dimensions, capturing essential patterns in the data while maintaining a compact feature space.

These steps produced multiple variations of the dataset, which are used for train various models. The source code of EDA and preprocessing of dataset can be find in `/source_code` folder. The preprocessed datasets are organized in the `/data/Preprocessed Datasets` folder, making it easy to reproduce results or test additional models.

## Models

In this project, we implemented a range of models to evaluate the performance on the phishing detection task. The models included both simple baseline models and more complex algorithms:

- Baseline Models: Logistic Regression and Support Vector Machine (SVM) were implemented as simple models to provide a performance baseline.

- Tree-Based Models: We also implemented more sophisticated tree-based models, including:
    - Random Forest
    - LightGBM
    - XGBoost

- Complex Models: For more advanced experimentation, we implemented a Multi-Layer Perceptron (MLP), a neural network-based model.

The training, tuning, and evaluation of these models were conducted on various preprocessed dataset variations. Additionally, feature importance analysis was performed to evaluate which features contributed most to the model’s predictions.

The source code for model training, tuning, and feature importance analysis can be found in the `/source_code` folder.

