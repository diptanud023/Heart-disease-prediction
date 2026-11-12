# Heart Disease Prediction

This project predicts whether a patient has heart disease from clinical measurements such as age, chest pain type, blood pressure and cholesterol. It compares logistic regression, random forest and XGBoost. I focused on recall rather than accuracy, because missing a patient who has heart disease is worse than flagging a healthy one for a follow-up check.


## Data
I used the UCI Heart Disease dataset (Cleveland, Hungarian, Switzerland and VA Long Beach), which has ___ rows after cleaning. The target was reduced to two classes: heart disease present or not. Cleaning steps:
- Removed ___ duplicate rows
- Treated zero values in cholesterol and resting blood pressure as missing, since zero is not a possible value
- Dropped the `ca` and `thal` columns because ___% and ___% of their values were missing
- Filled the remaining numeric gaps with the median, inside the model pipeline so the test data does not influence training

The dataset is not included in this repo. Download it from Kaggle: [add link].


## What I did
I split the data 80/20 into train and test sets, keeping the class balance in both. I compared the three models using 5-fold cross-validation on the training set, looking at recall, precision and ROC-AUC. I then evaluated the best model once on the held-out test set. Because the goal was to catch sick patients, I lowered the decision threshold until recall on the training data reached about 90%, and recorded how much precision dropped as a result.


## Results
| Model | Recall | Precision | ROC-AUC |
|---|---|---|---|
| Logistic Regression | ___ ± ___ | ___ ± ___ | ___ ± ___ |
| Random Forest | ___ ± ___ | ___ ± ___ | ___ ± ___ |
| XGBoost | ___ ± ___ | ___ ± ___ | ___ ± ___ |

On the test set, the tuned threshold of ___ raised recall from ___ to ___ and lowered precision from ___ to ___. The number of missed patients (false negatives) went from ___ to ___.

[2-3 sentences about what you actually found. For example: which model did best, whether the differences between models were larger than the ± ranges, and anything that surprised you or didn't work.]


## Limitations
- The dataset is small (___ rows), so differences between models are small and the results could change with a different split.
- The data comes from four hospitals with different measurement practices, and I did not test whether a model trained on one site works on another.
- This is a learning project. It has not been clinically validated and should not be used to make medical decisions.

## Run it
```
pip install -r requirements.txt
streamlit run app.py
```
