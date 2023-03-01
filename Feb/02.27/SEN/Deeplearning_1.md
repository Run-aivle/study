# 딥러닝
- 연결주의 학파(연결주의 알고리즘)
- 초기값 설정 많이 중요


## 선형회귀
```
# 라이브러리 선언
import tensorflow as tf
from tensorflow import keras
import numpy as np

# 1. 청소(세션 클리어) : 이전에 사용했던 모델이 있다면 없애줘
keras.backend.clear_session()

# 2. 모델 선언
model = keras.models.Sequential()

# 3. 모델 블록 조립
model.add(keras.layers.Input(shape = (1,)))
model.add(keras.layers.Dense(1))   # activation = 'linear'
## 오리지널 Sequential API 
# model.add( keras.layers.Dense(1, input_shape=(1,)) )

# 4. compile
model.compile(loss = 'mse', optimizer = 'adam')

# 학습
model.fit(x,y,epochs = 10, verbose = 1)

# 예측
y_pred = model.predict(x)
```
