# 📽️ MovieLens Recommendation System

## 📌 Project Overview
This project builds a **movie recommendation system** using the **MovieLens 32M dataset**.  
The current implementation focuses on **collaborative filtering** using **Alternating Least Squares (ALS)** in **Apache Spark**.  

The project consists of:
- **Exploratory Data Analysis (EDA)** to understand user behavior and rating distributions.
- **ALS-based recommendation modeling** with hyperparameter tuning.
- **Evaluation using RMSE & MAE** to select the best-performing model.

## 🛠️ Tech Stack
| Technology  | Purpose |
|-------------|---------|
| **Python**  | Core programming language |
| **Pandas, NumPy** | Data manipulation and preprocessing |
| **Matplotlib, Seaborn, Missingno** | Data visualization and missing value analysis |
| **Apache Spark (PySpark MLlib)** | Large-scale collaborative filtering with ALS |
| **Hyperopt** | Hyperparameter optimization for ALS |
| **MLflow** | Experiment tracking and model versioning |
| **AWS S3** | Storage for the MovieLens dataset |

## 📂 Dataset
We use the **MovieLens 32M dataset**, which contains:
- **Movies**: Metadata including titles and genres.
- **Ratings**: User-item interactions (user ID, movie ID, rating, timestamp).
- **Tags**: User-generated movie tags.

Data is **stored in AWS S3** and loaded directly into Spark for processing.

## 🔍 Exploratory Data Analysis (EDA)
- Analyzed **rating distributions**, **user activity**, and **movie popularity**.
- Identified **missing values** and checked for **data sparsity**.
- Visualized **genre trends** and **user preferences**.

## 🏗️ Model Development: ALS
- Used **Alternating Least Squares (ALS)** from **PySpark MLlib**.
- Trained the model using **user-item interactions (raw ratings data)**.
- **Fine-tuned hyperparameters** (rank, regularization, iterations) using **Hyperopt**.
- Evaluated performance using **Root Mean Squared Error (RMSE)** and **Mean Absolute Error (MAE)**.
- Selected the model with the **lowest MAE and very low RMSE**.

## 🚀 Next Steps
🔹 Incorporate **content-based features** like **tags and genres** for a hybrid approach.  
🔹 Experiment with **ranking-based evaluation metrics**.  
🔹 Deploy the model as an **API on AWS (Lambda/SageMaker)** for real-time recommendations.

## 📜 How to Run
### 1️⃣ Setup Environment
```bash
pip install boto3 s3fs pandas numpy matplotlib seaborn pyspark hyperopt mlflow
```
### 2️⃣ Run EDA
python MovieLens_EDA.ipynb

### 3️⃣ Train ALS Model
python als_fine_tune.ipynb

🏆 Results
The best ALS model achieved:

Low RMSE and MAE, indicating accurate predictions.
Scalability with Spark, handling millions of interactions efficiently
