---
title : "[ML] - Simple Regression"
excerpt: "선현 회귀 모델에 대해 알아보도록 하겠습니다."
toc : true 
toc_sticky: true
header:
    teaser: /assets/ml.jpg

category :
    - ML
tag : 
    - Linear Regression
    - Independent variable
    - Dependent variable
    - Positive Relationship
    - Negative Relationship
    - Ordinary Least Regression
    - Tabular data
---

# 개요
<img src='/assets/ml.jpg' width = 1000 height = 800 >

**선형 회귀** 모델에 대한 이해하고 Scikit-learn을 이용해서 선형 회귀 모델을 만들어 보겠습니다. 특히, **종속 변수와 독립 변수**, 회귀선을 이루고 있는 **회귀 계수**를 주의 깊게 살펴보겠습니다.

그리고 **Least Square** 방법이 무엇인지에 대해서도 알아보겠습니다.

이번 내용에서 사용할 데이터 셋
- 미국 시애틀 King County 지역에서 2014년 5월부터 ~ 2015년 5월까지 주택 판매 가격
```py
import pandas as pd
df = pd.read_csv('https://ds-lecture-data.s3.ap-northeast-2.\amazonaws.com/kc_house_data/kc_house_data.csv')
df.head()
```
<img src='/assets/dataframe4.PNG' width = 1000 >

<br/>

# Linear Regression 

## 1. 독립변수 & 종속변수

독립변수와 종속변수 간의 관계에 대해서 알아보겠습니다.]

### 1-1. Positive Relationship & Negative Relationship
>Positive Relationshop
: 독립변수가 증가함에 따라 종속변수도 증가하는 관계를 뜻한다.
<img src='/assets/pr.PNG' width = 1000 >

>Negative Relationshop
:독립변수가 증가함에 따라 종속변수가 감소하는 관계를 뜻한다.
<img src='/assets/nr.PNG' width = 1000 >

### 1-2. coefficient & intercept 
>회귀 직선
$\displaystyle {\hat {y}} =\beta_0 + \beta_1{x}$

해당 직선에 $\beta_0(기울기)$와 $\beta_1(회귀 계수)$의 의미를 파악해보자. 


> 종속변수: price, 독립변수: sqft_living
```py
import numpy as np
print(f'y = {model_sqft.coef_[0][0]:.02f}x - {np.abs(model_sqft.intercept_[0]):.02f}')
#output 
y = 280.62x - 43580.74
```
독립변수(sqft_living)와 종속변수(price)간의 회귀직선에서 회귀계수와 y절편을 확인할 수 있다. 회귀계수를 통해 알 수 있는 내용은 1 sqft당 280$가 증가한다고 해석할 수 있다. **종속변수와 독립변수가 서로 비례 관계임을 확인할 수 있다.**


## 2. Oridinary Least Square

<img src='/assets/regressionline.PNG' width = 600 >

>[OLS 구하는 공식]

$\beta =\displaystyle {\bar {y}}-\alpha{\bar {x}}$

$\alpha ={\frac {S_{xy}}{S_{xx}}}$

${\displaystyle S_{xy}=\sum _{i=1}^{n}(x_{i}-{\bar {x}})(y_{i}-{\bar {y}})}$ 

${\displaystyle S_{xx}=\sum _{i=1}^{n}(x_{i}-{\bar {x}})^{2}}$

우리가 머신러닝 방법 중에 하나인 Linear Regression을 통해 하고자 하는 것은 데이터의 **예측**이다. 예측을 위해 주어진 데이터에 가장 **fit**한 선형회귀직선을 해당 방법을 이용해 구하려고 하는 것이다. 

이러한 회귀 직선을 구하기 위해서 우리가 사용하는 방법을 **OLS**라고 한다. OLS에 대해 간단히 언급해보겠다.

**OLS(Ordinary Least Square)란**, 간단히 이해하면 최소값을 찾는 것이다. 여기서 중요한 것은 어떤 값의 **최솟값**을 찾으려고 하는지이다.

우리는 단순선형회귀모델을 만들고 해당 모델의 계수와 절편을 통해 회귀직선을 알 수 있다. 우리가 최종적으로 원하는 선형모델은 실제값과 예측값간의 차이가 최소화되는 것을 원한다. 그래서 구한 회귀직선과 실제값간의 거리가 최소화되는 회귀직선을 찾기 위해 우리는 데이터를 이용해 **학습**이라는 것을 진행한다.

위에서 언급한 회귀직선과 실제값간의 거리를 우리는 **에러 또는 잔차**라고 부른다. 이러한 잔차가 최소화되는 선이 무엇인지를 찾기 위해 우리는 **OLS**를 사용한다. 즉, 모든 실제 데이터와 회귀직선간의 거리의 제곱의 합이 제일 작아지는 그 때의 회귀직선을 우리는 구하려고 하는 것이고 이 때 우리는 **OLS라는 방법**을 사용하게 된다.



>RSS & SSE & Cost Function?

OLS에 대해 공부하다보면 **RSS, SSE, Cost Function**이란 용어를 확인할 수 있을 것이다. 각 용어가 무엇을 의미하는지 살펴보겠다. 

1. RSS(Residual Sum of Squares) & SSE(Sum of Square Error)
**RSS**는 말 그대로 잔차 제곱의 합을 의미하고 **SSE**는 에러 제곱의 합을 의미한다. 잔차와 에러 둘다 머신러닝에서 의미하는 바는 같기 때문에 **두 용어의 의미는 동일**하다고 생각하면 된다. 

2. Cost Function 
**Cost Function**은 회귀모델의 비용함수인데, 여기서 비용함수가 결국 RSS & SSE를 의미한다. 결국 3 용어가 가지는 의미가 모두 비슷하다는 것을 확인할 수 있다. 

**머신러닝에서의 학습은 사용하고자 하는 모델의 비용함수를 최소화하는 모델을 찾는 과정을 말한다.**
