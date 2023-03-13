# CNN
- ComputerVision
- 조각을 보고, 각 조각의 조합된 패턴, 점점 더 복잡한 조합의 패턴, 반응하는 여러 패턴의 조합을 통해 이미지를 인식
- Computer Vision
    - FeiFeiLi : ImageNet
    - YannLecnn :
        - LeNet
        - AlexNet
        - (Convolutional, Neural, Network)

### Filter(Convolution)
- 고차원의 필터를 생성하는것
- Filter의 수는 사용자 지정

### stride
- 필터의 이동을 조절
- Stride를 하는 이유? 연산량을 줄이기 위해
- output size = (N-F)/Stirde + 1

### Padding
- 외곽의 정보를 반영
- 이미지의 size를 유지하기 위해
- (F-1)/2로 padding 수 계산

### Pooling(sub sampling)
- 연산량을 줄이기 위해
- MAX, AVG
