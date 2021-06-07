---
title : "[Data Science] - statistic1"
category :
    - Data Science 
tag : 
    - hypothesis test
    - statistic
    - descriptive statistics
    - inferential statistics
    - sampling
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

<img src='/assets/datascience.png' width = 1000 height = 800 >

#### 개요 

1.통계의 **2**가지 종류에 대해 알아보겠습니다.
- Statistics 
    - Descriptive Statistics
    - Inferential Statistics 

2.**sampling**에 대해서도 알아보겠습니다.    

##### 1. 통계 

**통계**는 데이터를 다루는 목적에 따라서 크게 **기술 통계**와 **추리 통계**로 나뉠 수 있습니다.

##### 1-1. 기술 통계(Descriptive Statistics)

기술 통계에서 **기술**은 **Technology**가 아닌 **Descriptive**를 뜻한다. 따라서 **기술 통계**란 우리가 수집한 데이터를 **묘사, 설명**하는 통계 기법을 말한다.

기술 통계는 크게 **2** 가지로 나눠질 수 있다. 

##### 1-1-1. 데이터의 집중화 경향에 대한 기법

우리가 수집한 데이터를 대표하는 값이 무엇인지, 어떤 값에 집중되어 있는지를 다루는 기법이다. 대표적인 기법으로는 **평균, 중앙값, 최빈값, 등**이 있다.

##### 1-1-2. 데이터가 어떻게 퍼져 있는지를 설명하는 기법

이러한 기법을 **분산도**라고 한다. 말 그대로 데이터가 전반적으로 **어떻게 분포**되어 있는지를 설명하는 방법이다. 대표적으로 **표준편차(standard deviation), 사분위(quartile) 등**이 있다.

다양한 기술 통계 기법을 시각화를 할 수 있다. [이곳](https://github.com/junginkim23/ds-section1-sprint2/blob/master/n121-hypothesis-test/n121-hypothesis-test.ipynb)을 가면 관련 시각화 그림을 살펴 볼 수 있습니다.

>해당 기술 통계치를 코드를 통해 잠깐 살펴보자. describe()함수를 사용하면 쉽게 기술 통계치들을 확인할 수 있다.

```py
import numpy as np

v = np.random.randint(0,100,20)
pd.DataFrame(v).describe()
#output:
	0
count	20.000000
mean	36.050000
std	28.601573
min	1.000000
25%	13.000000
50%	30.000000
75%	57.750000
max	96.000000
```

ps)편차가 크다는 것은 분포가 넓게 분포되어 있다는 뜻이고 곧 이말은 분배가 골고루 이루어 지지 않고 있다고 볼 수 있다.

##### 1-2. 추리 통계(Inferential Statistics)

**추리 통계**란 수집한 데이터를 바탕으로 **추론 예측**하는 통계 기법을 말한다. 대표적인 추리 통계의 예로는 대통령 선거 예측을 들 수 있다.

<img src='/assets/president.PNG' width = 1000 height = 800 >

해당 그림은 해당 블로그를 [참조](https://eretail.tistory.com/454)하였습니다.

**추리 통계**를 통해 힐러리와 트럼프 중 누가 당선될지를 예측했고 예측 결과와 달리 트럼프가 당선이 되었습니다. 결국 추리 통계는 확률일 뿐이였습니다. 이러한 이유에는 적은 표본을 비롯한 여러 가지 이유가 있을 것입니다. 여기서 중요한 것은 추리 통계를 통해 결과를 맞추고 안 맞추고를 떠나서 **추리 통계 또한 중요한 통계 기법중에 하나**라는 것입니다.

#### 2. sampling

sampling을 하는 이유는 큰 모집단에서 표본 집단을 뽑기 위해서 인데, 모집단의 많은 양의 데이터를 모두 수집하기에는 힘들기 때문에 특정 집단만을 뽑아서 표본 집단으로 사용한다. 

sampling을 종류에는 크게 **4** 가지가 존재한다. 

>Simple Random Sampling
: 모집단에서 sampling을 무작위로 하는 방법이다.

>Systematic Sampling
: 모집단에서 sampling을 할 때 규칙을 가지고 추출하는 방법이다. 

>Stratified(층층이) Random Sampling
: 모집단을 미리 여러 그룹으로 나누고 그 그룹별로 무작위 추출을 수행하는 방법이다.
: 대표적인 예로 여론 조사를 위해 사람을 나이대별로 나누고 해당 그룹안에서 무작위로 추출하는 것을 들 수 있다. 

>Cluster Sampling 
: 모집단을 미리 여러 그룹으로 나누고, 이후 특정 그룹을 무작위로 선택하는 방법이다. 

