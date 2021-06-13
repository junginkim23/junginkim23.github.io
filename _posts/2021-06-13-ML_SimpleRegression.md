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
    - EDA
    - Data-Processing
    - tidy data 
    - wide data
    - filtering
    - groupby
    - isin
    - melt
    - pivot_table

---

# 개요
<img src='/assets/ml.jpg' width = 1000 height = 800 >

**선형 회귀** 모델에 대한 이해하고 Scikit-learn을 이용해서 선형 회귀 모델을 만들어 보겠습니다. 특히, **종속 변수와 독립 변수**, 회귀선을 이루고 있는 **회귀 계수**를 주의 깊게 살펴보겠습니다.

그리고 **Least Square** 방법이 무엇인지에 대해서도 알아보겠습니다.

<br/>

# Linear Regression 

## 독립변수 & 종속변수

독립변수와 종속변수 간의 관계에 대해서 알아보겠습니다.]

### Positive Relationship
독립변수가 증가함에 따라 종속변수도 증가하는 관계를 뜻한다.

### Negative Relationshop 
독립변수가 증가함에 따라 종속변수가 감소하는 관계를 뜻한다.

## Regression Line 
<img src='/assets/regressionline.png' width = 600 >

독립변수와 종속변수의 따라 놓여져 있는 데이터에 가장 적합한 회귀선을 구한 그림이다. 회귀선을 구하기 위해서는 **least square method**를 사용한다.

가장 적합한 회귀선을 구하는 방법은 실제값과 회귀선 사이의 거리(잔차 or 에러)의 제곱이 합이 최소가 되는 회귀선을 구하면 된다.

### least square method? 

위에서 언급한 실제값과 예측값 사이의 거리를 구하는 방법이 least square method이다. 이 방법은 우리가 구하고자 하는 값을 최소화 시킬 수 있다.

