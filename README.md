# README.md

# Predicting Airplane Delays

## Project Overview

This project aims to predict flight delays caused by weather for a U.S.-based travel booking platform. By developing a machine learning model, the company can notify customers of potential delays during the booking process. The dataset used contains flight details from 2014 to 2018, with additional features such as weather and holiday indicators added to improve predictive accuracy.

## Goals

1. Process and combine multiple datasets to create a clean, usable dataset.
2. Perform exploratory data analysis (EDA) to understand patterns in the data.
3. Develop baseline and advanced classification models to predict flight delays.
4. Compare model performance metrics, including accuracy, precision, recall, and AUC, to determine the best-performing model.
5. Address the issue of class imbalance to enhance the model’s ability to detect delays accurately.

## Dataset

The dataset consists of U.S. domestic flight information, covering 60 compressed files containing monthly data for 2014-2018. The dataset was compiled by the Bureau of Transportation Statistics (BTS), and additional weather data was sourced from the National Centers for Environmental Information (NCEI).

## Installation

1. Clone the repository.
2. Ensure you have the following Python libraries installed:
   - `pandas`
   - `numpy`
   - `matplotlib`
   - `seaborn`
   - `scikit-learn`
3. Download the dataset files from [this link](https://ucstaff-my.sharepoint.com/:f:/g/personal/ibrahim_radwan_canberra_edu_au/Er0nVreXmihEmtMz5qC5kVIB81-ugSusExPYdcyQTglfLg?e=bNO312) and place them in the `data/data_compressed` folder.

## Code Structure

The notebook is divided into the following main sections:

1. **Problem Formulation**: Defines the business problem and outlines the machine learning approach.
2. **Data Preprocessing**: Loads and cleans data, handles missing values, and filters relevant features.
3. **Feature Engineering**: Adds holiday indicators and weather data, and applies one-hot encoding to categorical features.
4. **Model Training and Evaluation**: Trains a logistic regression model with and without resampling techniques to address class imbalance, then evaluates model performance.
5. **Results and Analysis**: Compares models using various metrics to determine the best-performing model.
6. **Tableau Visualization**: Visualizes key patterns in the data to aid in understanding delay factors.

## Running the Code

1. **Data Processing and Preprocessing**:
   - Extract CSV files from the compressed ZIP files.
   - Combine multiple CSVs into a single dataset by filtering relevant columns and rows.
   
2. **Feature Engineering**:
   - Create indicators for weather conditions and public holidays.
   - Apply one-hot encoding to categorical variables.

3. **Model Training and Evaluation**:
   - Train logistic regression models on imbalanced data, data with additional weather features, and balanced data using resampling.
   - Evaluate each model using accuracy, precision, recall, specificity, and AUC.

4. **Visualization with Tableau**:
   - Use the final combined dataset (`combined_csv_v2.csv`) to create a Tableau dashboard that visualizes the impact of various factors on delays.

## Expected Outputs

1. **Exploratory Data Analysis**:
   - Visualizations showing distributions for delay vs. no delay by month, time of day, day of the week, airline, origin and destination airports, and distance.
   
2. **Model Evaluation**:
   - Confusion matrix and ROC curve for each model.
   - Key metrics displayed for each model to compare performance, with emphasis on recall due to the focus on delay prediction.

3. **Results Comparison Table**:
   | Metric                   | Initial (Imbalanced Data) | Imbalanced + Weather Features | Sampled (Balanced Data) |
   |--------------------------|---------------------------|-------------------------------|--------------------------|
   | **Accuracy**             | 0.7901                    | 0.7908                        | 0.5988                   |
   | **Precision**            | 0.5351                    | 0.5206                        | 0.6297                   |
   | **Recall (Sensitivity)** | 0.0021                    | 0.0407                        | 0.4797                   |
   | **Specificity**          | 0.9995                    | 0.9900                        | 0.7180                   |
   | **AUC**                  | 0.63                      | 0.63                          | 0.63                     |

4. **Tableau Visualization**:
   - Link: [Tableau Dashboard](https://public.tableau.com/views/u3265713_Tableau_Dashboard/Dashboard1?:language=en-GB&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

## Key Learnings

1. **Handling Class Imbalance**: Addressing imbalanced classes is critical for real-world scenarios where the minority class (flight delays) holds more significance.
2. **Importance of Evaluation Metrics**: Metrics like recall, specificity, and AUC provide more insight than accuracy alone when dealing with imbalanced datasets.
3. **Feature Engineering**: Incorporating domain-specific features such as weather and holidays enhances the model's predictive power by providing additional context.

## Future Improvements

- **Resampling Techniques**: Apply advanced methods like SMOTE for a more balanced dataset.
- **Alternative Algorithms**: Test models such as random forests or XGBoost to handle complex data patterns.
- **Hyperparameter Tuning**: Use grid search or other optimization techniques to fine-tune the model for improved recall.

---

