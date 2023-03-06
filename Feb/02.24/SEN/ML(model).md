# 지도학습 종류
## 분류
- Logistic Regressor
- DecisionTree Classifier
- SVC
- KNeighbor Classifier
- RandomForest Classifier
- XGBoost Classifier
- LGBM Classifier



## 회귀
- Linear Regressor
- DecisionTree Regressor
- SVR
- KNeighbor Regressor
- RandomForest Regressor
- XGBoost Regressor
- LGBM Regressor

**분류 회귀 문제 파악하고, 맞는 모델과 성가지표 사용하기**

# 파라미터 튜닝
- RadomSearchCV
  - 범위에 있는 값들 중 랜덤으로 선택하여 튜닝
  ```
  parmas = {'파라터': 값}
  model = RandomSerchCV(model,
                        params,
                        cv = 5,
                        n_iter = 20)
  ```
- GridSearchCV
  - 범위에 있는 모든 값들로 튜닝
  ```
  parmas = {'파라터': 값}
  model = RandomSerchCV(model,
                        params,
                        cv = 5)
  ```
