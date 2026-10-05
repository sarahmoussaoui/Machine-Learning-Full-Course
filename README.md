# Machine Learning Full Course

A collection of hands-on machine learning projects: a neural network for regression (TensorFlow/Keras) and a gradient boosting classifier (CatBoost). Each project has its own folder with notebooks, scripts, and data.

## Table of Contents

- [Repository Structure](#repository-structure)
- [Projects](#projects)
  - [1. Artificial Neural Network: Power Plant Energy Prediction](#1-artificial-neural-network-power-plant-energy-prediction)
  - [2. CatBoost: Breast Cancer Classification](#2-catboost-breast-cancer-classification)
- [Getting Started](#getting-started)

## Repository Structure

```
.
├── Artificial_Neural_Network project/
│   └── Final Folder/
│       ├── ANN_Architecture.png
│       ├── Codes/
│       │   ├── artificial_neural_network.ipynb
│       │   └── artificial_neural_network.py
│       └── Dataset/
│           └── Folds5x2_pp.xlsx
├── CatBoost/
│   ├── Data.csv
│   ├── catboost.ipynb
│   └── catboost.py
├── .gitattributes
├── .gitignore
└── README.md
```

## Projects

### 1. Artificial Neural Network: Power Plant Energy Prediction

A fully connected neural network that predicts the net hourly electrical energy output of a combined cycle power plant (regression).

- **Dataset:** `Folds5x2_pp.xlsx`, 9,568 rows
- **Features:** Ambient Temperature (`AT`), Exhaust Vacuum (`V`), Ambient Pressure (`AP`), Relative Humidity (`RH`)
- **Target:** Net hourly electrical energy output (`PE`)
- **Split:** 80% train / 20% test (`random_state = 0`)
- **Architecture:** Dense(6, ReLU) → Dense(6, ReLU) → Dense(1), shown in `ANN_Architecture.png`
- **Training:** Adam optimizer, mean squared error loss, batch size 32, 100 epochs
- **Result:** the training loss drops from about 82,111 in epoch 1 to about 26.7 by epoch 100, and test predictions closely follow the real values (for example, predicted 430.79 vs. actual 431.23)

**Run it:** open `Codes/artificial_neural_network.ipynb` (or run `artificial_neural_network.py`) from the `Codes/` folder with the dataset path adjusted to `../Dataset/Folds5x2_pp.xlsx`.

### 2. CatBoost: Breast Cancer Classification

A CatBoost gradient boosting classifier that predicts whether a tumor is benign or malignant.

- **Dataset:** `Data.csv`, 682 samples with 9 cytological features (Clump Thickness, Uniformity of Cell Size, Uniformity of Cell Shape, Marginal Adhesion, Single Epithelial Cell Size, Bare Nuclei, Bland Chromatin, Normal Nucleoli, Mitoses)
- **Target:** `Class` (2 = benign, 4 = malignant)
- **Split:** 80% train / 20% test (`random_state = 0`)
- **Model:** `CatBoostClassifier` with default parameters
- **Evaluation:** confusion matrix, accuracy score, and 10-fold cross-validation (mean accuracy and standard deviation)

**Run it:** open `catboost.ipynb` (or run `catboost.py`) from the `CatBoost/` folder.

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/sarahmoussaoui/Machine-Learning-Full-Course.git
   cd Machine-Learning-Full-Course
   ```

2. (Optional) Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
   ```

3. Install the dependencies:
   ```bash
   pip install numpy pandas matplotlib scikit-learn tensorflow catboost openpyxl jupyter
   ```
   (`openpyxl` is needed to read the `.xlsx` dataset.)

4. Launch Jupyter and open the notebook of the project you want to run:
   ```bash
   jupyter notebook
   ```
