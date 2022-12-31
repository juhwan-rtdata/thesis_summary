# 3. 선형 모델
## 3.1 기본 형식
- d개의 속성을 가진 샘플 x=(x<sub>1</sub>; x<sub>2</sub>; ...; x<sub>d</sub>)이 있고 x<sub>i</sub>는 x의 i번째 속성을 가진 값이라고 가정
- 선형 모델 : 속성들의 선형 조합을 통해 예측하는 함수를 학습하는 모델이라고 정의할 수 있음
  - $$f(x) = w_{1}x_{1}+w_{2}x_{2}+...+w_{d}x_{d}+b$$
  - 벡터 형태로 된 수식 : $$f(x)=w^Tx+b$$
    - w=(w<sub>1</sub>; w<sub>2</sub>; ...; w<sub>d</sub>;)이며 w와 b를 학습한 후 모델이 결정
- 선형 모델의 특징
  - 형식이 매우 간단, 모델을 만들기 쉬움
  - 머신러닝의 중요한 기본 사상을 담고 있음
  - w는 예측에 있어서 각 속성의 중요성을 직관적으로 드러냄
    - 해석능력이 뛰어남
- 비선형 모델 : 선형 모델을 기반으로 하여 층을 쌓아 올리거나 고차원으로 투영하여 만들어짐

## 3.2 선형 회귀
- 선형 회귀(linear regression)
  - 목표 : 최대한 정확하게 실제 데이터를 예측하는 선형 모델을 학습하는 것
  - 데이터 세트 D는 {(x<sub>1</sub>,y<sub>1</sub>),(x<sub>2</sub>,y<sub>2</sub>),...,(x<sub>m</sub>,y<sub>m</sub>)}으로 정의
    - x<sub>i</sub> : (x<sub>i1</sub>; x<sub>i2</sub>; ...; x<sub>id</sub>), y<sub>i</sub> ∈ IR로 정의
- 선형 회귀는 다음과 같은 함수를 학습함
  - $$f(x_{i})=wx_{i}+b을 통해 f(x_{i}) \simeq y_{i}을 얻음 $$
  - w와 b는 어떻게 정해지는가?
    - f(x)와 y의 차이를 어떻게 측정하느냐에 달렸음
- 평균제곱 오차 -> 회귀 문제에서 가장 자주 사용하는 성능 측도
  - 평균제곱 오차를 최소화하는 방법

$$ w^\*, b^\* = argmin_(w,b) \displaystyle\sum_{i=1}^{m} (f(x_{i})-y_{i})^2 = argmin_(w,b) \displaystyle\sum_{i=1}^{m} (y_{i}-wx_{i}-b)^2$$

- 평균제곱 오차 : 기하학적인 의미
  - 유클리드 거리를 사용하기 때문
- 최소제곱법(least square method) : 평균제곱 오차를 최소화하는 방법으로 모델의 해를 구하는 방법
  - 선형 회귀에서의 목표 : 샘플과의 유클리드 거리의 합이 가장 작은 하나의 직선을 찾는 것
  - w와 b의 해를 찾는 것 
    - $$E_(w,b) = \displaystyle\sum_{i=1}^{m} (y_{i}-xw_{i}-b)^2를 최소화하는 과정$$ 
    - 이를 선형 회귀 모델의 최소제곱 파라미터 예측이라고 부름
    - E<sub>(w,b)</sub>로 w와 b에 대한 식
      - $$\frac{\partial E_(w,b)}{\partial w}= 2(w\displaystyle\sum_{i=1}^{m} x_{i}^2 - \displaystyle\sum_{i=1}^{m}(y_{i}-b)x_{i})$$
      - $$\frac{\partial E_(w,b)}{\partial b}= 2(mb - \displaystyle\sum_{i=1}^{m} (y_{i}-wx_{i}))$$
    - w와 b에 대한 식을 0으로 만들어 w와 b 최적해(optimum solution)의 닫힌 해(closed-form solution)를 구할 수 있음
      - $$w=\frac{\displaystyle\sum_{i=1}^{m} y_{i}(x_{i}- \overline{x})}{\displaystyle\sum_{i=1}^{m} x_{i}^2 - \frac{1}{m}(\displaystyle\sum_{i=1}^{m} x_{i})^2}$$
      - $$b=\frac{1}{m}\displaystyle\sum_{i=1}^{m}(y_{i}-wx_{i})$$
