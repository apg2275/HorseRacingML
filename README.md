# HorseRacingML

The horse racing dataset used was sourced from Kaggle named "Horse Racing in HK". It contains racing records of every horse race event that occurred between June 2nd, 1997, and approximately August 7th, 2005, from two race tracks in Shatin and Happy Valley. You can access and download the dataset [here](https://www.kaggle.com/gdaley/hkracing).

Given that many models related to horse racing focus solely on the first place finish when there are many other types of betting strategies available. Some may end up having a higher expected value resulting in the better betting strategies focusing on more than just solely the first place. 

Because of this, exploration into which model performs best for different betting type and overall seemed like an underlooked aspect.

As well, this project served as a way to familiarize myself with the different machine learning models, libraries, and overall methodologies used when creating models to try and solve a real world problem.

# Betting Strategy Types

Explanation of betting strategies used in the project:

- **Win**: Horse that will finish in first place.
- **Place**: Horse that will finish in either first or second place.
- **Show**: Horse that will finish in first, second, or third place.
- **Exacta**: Predicting the horses that will finish in first and second, in the exact order.
- **Quinella**: Predicting the horses that will finish in first and second, regardless of the order.
- **Trifecta**: Predicting the horses that will finish in first, second, and third, in the exact order.
- **Boxed Trifecta**: Predicting the horses that will finish in first, second, and third, in any order.


# Types of models
Most models were hyperparameter tuned using Optuna


- Regression
	- Least Squares Regression
	- Elastic Net|Elastic Net Regression
	- Logistic Regression
	- XGBoost Regression
	-  CatBoost Regression
	-  LightGBM Regression
	- AdaBoost Regression
- Classification
	- KNN
	- Naive Bayes
	- SVM
	- AdaBoost Classifier
	- Random Forests
	- XGBoost Classifier
	- CatBoost Classifier
	- LightGBM Classifier
- Ranking
	- XGBoost Ranking
	- CatBoost Ranking
	- LightGBM
- Ensemble
	- Classification
	- Regression
	- Ranking
- Neural Networks (Tensorflow)
	- Classification
	- Regression


# Results

Models were evaluated based on their accuracy across various betting types, as well as their geometric mean. A model could potentially predict every horse as a winner, leading to a 100% win rate but this would reflect in other metrics such as quinella or exacta being 0 or close to 0. Checking the accuracy, precision, f1, and geometric mean for each model helped inform the decision for which model was better suited for each betting type. Exact numbers for each model can be see in the notebook.

For the overall best general model, geometric mean was used as the deciding factor.

- Win:  AdaBoost Classifier
- Place: XGBoost Classifier
- Show: XGBoost Classifier
- Exacta: XGBoost Classifier
- Quinella: XGBoost Classifier
- Trifecta: LightGBM or XGBoost Regression
- Boxed Trifecta: SVM
- Geometric mean: XGBoost Classifer
