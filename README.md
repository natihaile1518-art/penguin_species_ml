# Penguin Species Detection using Random Forest

## Project Objective
This project is based on the **Edureka Machine Learning course**.  
I have recreated this project and added **clear markdown explanations** to make it easy to understand the concepts behind the model.

The goal is to build a machine learning model that behaves like a biologist: it predicts the species of penguins based on their body measurements.

## Dataset
We use the **penguins dataset** from seaborn, containing 344 samples and 7 features:
- island
- sex
- bill_length_mm
- bill_depth_mm
- flipper_length_mm
- body_mass_g
- species (target)

Missing values are removed, and categorical features are encoded numerically.

## Feature Engineering
- **Sex:** One-hot encoding (`0` = female, `1` = male)  
- **Island:** One-hot encoding (`Biscoe`, `Dream`, `Torgersen`)  
- Categorical columns are dropped after encoding

The final feature set contains numeric columns only, ready for the model.

## Target Variable
- `species` is the target variable  
- Encoded numerically:
  - `Adelie` → 0
  - `Chinstrap` → 1
  - `Gentoo` → 2

## Model
- **Random Forest Classifier** with `n_estimators=5`, criterion=`entropy`, random_state=0
- Trained on **70%** of the data, tested on **30%**

### Why Random Forest?
- Ensemble method of multiple decision trees  
- Reduces overfitting compared to a single decision tree  
- Can handle both classification and regression tasks  
- Good accuracy without needing normalization

## Training / Testing
- `X_train`, `y_train` → training data  
- `X_test`, `y_test` → unseen data for evaluation  
- Random state ensures reproducible splits

## Results
- Accuracy: 98%  
- Confusion Matrix shows almost all penguins correctly classified:

| Species    | Correct Predictions | Total in Test Set |
|------------|------------------|-----------------|
| Adelie     | 47               | 48              |
| Chinstrap  | 17               | 18              |
| Gentoo     | 34               | 34              |

- Classification report provides **precision**, **recall**, and **F1-score** for each class.

## Important Random Forest Terms
- **Root Node:** Where training data enters  
- **Splitting Node:** Uses Gini or entropy to decide split  
- **Decision Node:** Provides branch direction  
- **Leaf Node:** Final prediction

### Advantages
- Low variance  
- Reduces overfitting  
- No need for normalization  
- High accuracy

### Disadvantages
- Requires more training time  
- Complex interpretation  
- High memory usage  
- Computationally expensive

## How to Run
1. Install required packages: `pandas`, `numpy`, `seaborn`, `scikit-learn`  
2. Run the notebook `Hands_on_penguin.ipynb` step by step  
3. Model predicts species for unseen penguin data

## Notes
- This project is directly inspired by the Edureka course.  
- I prepared this project with **clear markdown explanations** to make it easier for beginners to understand Random Forest concepts.

## Author
Natnael Haile  
Data Science Student | Bahir Dar University, Ethiopia  