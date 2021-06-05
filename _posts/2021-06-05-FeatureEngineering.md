---
title : "[Data Science] - Feature Engineering"
category :
    - Data Science 
tag : 
    - Feature Engineering
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

### Feature Engineering  

데이터 사이언티스트 또는 데이터 직군에서 일하는 사람들이 가장 많이 소비하는 시간은 **Data cleaning**하는 시간이다. 

그 이유는 실세계의 데이터는 엄청 엉망진창이고 복잡하기 때문이다. 만약 데이터가 너무 엉망진창하고 복잡하다면 우리가 훗날 머신러닝 모델에서 사용하기가 어렵다. 그래서 우리가 사용하고자 하는 데이터로 수정, 가공해줘야 한다.

**Feature Engineering**이 Data Cleaning을 돕는다.

#### Feature Engineering의 여러 가지 방법 중 3가지

**Feature Engineering**은 수학, 통계, 그리고 도메인 지식을 사용해서 raw data로부터 유용한 특징을 추출하는 과정이다. Data Cleaning을 하는 과정에 포함되는 프로세스라고 이해하면 좋을 것 같다.

##### 1. Outlier detection 

- Domain Knowledge을 활용 
- Visualization 활용
- Math/Statistics: Two standard deviation 활용

위의 3가지 방법을 통해 이상치를 감지할 수 있다.

##### 2. Handling missing values

- 결측값 삭제
- 나머지 실값의 평균으로 대체

##### 3. One Hot Encoding(category -> numeric)

범주형 데이터를 이용해서 머신러닝 모델을 트레이닝 시킬 수 없다. 머신모닝 모델은 범주형 데이터를 이해하지 못하기 때문이다. 그래서 범주형 데이터를 수치형 데이터로 바꿔준다.