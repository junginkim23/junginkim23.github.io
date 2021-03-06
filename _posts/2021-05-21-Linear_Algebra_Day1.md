---
title : "[Data Science] Linear Algebra"
excerpt: "선형대수학이 무엇인지, 벡터란 무엇인지 등 선형대수학의 기초 개념을 살펴보자."
header:
    teaser: /assets/datascience.png
# author_profile: true
# sidebar:
#   nav: "sidebar-contents"
category :
    - DS
tag : 
    - Linear Algebra
    - vector
    - matrix
toc : true 
toc_sticky: true
---

<img src='/assets/datascience.png' width = 1000 height = 800 >

## [알고 지나가야 하는 개념]
- Linear Algebra?
- Vector? 
- numpy
- Identity Matrix
- Determinant
- Inverse Matrix 
- Word2Vec?
- Determinant 0 & Data Redundancy

##### 선형대수학이란?
- 선형대수학의 사전적 정의
    - 벡터 공간, 벡터, 선형 변환, 행렬, 연립 선형 방정식 등을 연구하는 대수학의 한 분야이다. 현대 선형대수학은 그 중에서도 벡터 공간이 주 대상이다.

- 필연적으로, 수학을 왜 하는지에 대한 철학적인 질문부터 시작되어야 한다. 여기서 수학이란 인과관계를 수를 이용하여 이해하고 표현하려고 하는 학문이라고 생각한다.

- 인과관계라고 하면 인간의 입장에서 명확하게 파악하기 위해서는 선형적인 관계밖에 없다고 볼 수 있다.

- 선형대수학은 데이터 분석가에게 많은 숫자의 배열을 시각적으로 개념화하기 좋은 방법을 제공합니다. 데이터 속의 패턴을 설명하고, 어떤 연산들에 대한 보편적인 관점을 제공합니다.

##### vector?
- 선형대수학의 가장 기본이 되는 것 

- 벡터를 바라보는 3가지 관점 
    1. 물리학자의 관점 
        - 공간 상의 한 화살표 : 한 벡터는 그 길이와 그것이 가리키는 방향으로 결정됩니다. 이 두 요소(길이와 방향)가 같다면 벡터를 아무데나 옮긴다 하더라도 여전히 같은 벡터로 취급합니다.
    2. 컴퓨터 과학자의 관점
        - 배열/리스트의 자료구조로 나타냅니다. 컴퓨터 과학자의 관점에서 바라본 벡터는 배열/리스트의 구조로 나타내어지기 때문에 순서가 중요해지게 됩니다. 같은 값을 가질지라도 순서가 다르면 다른 벡터로 판단될 수 있습니다.
    3. 수학자의 관점
        - 벡터를 바라보는 물리학자의 관점과 컴퓨터 과학자의 관점을 일반화합니다. 즉, 기본적으로 무엇이든 벡터가 될 수 있습니다. 두 벡터끼리의 곱, 합, 그리고 나중에 다루게 될 연산이 성립되는 모든 것들을 지칭합니다. 다소 추상적인 관점이기 때문에 이 관점에 대해 집중하는 것보다는 구체적인 개념에 집중하는 것이 좋습니다.
    

- 벡터를 떠올릴 때는 xy평면 같은 좌표계에 있는 꼬리가 원점에 고정된 화살표를 떠올리세요! 물리학자의 관점과 달리 아무데나 위치할 수 있지 않고 꼬리가 원점에서 고정되어 있어야 합니다.

**벡터의 덧셈과 상수배가 선형대수학에서 중요한 역할을 한다.**
- 벡터의 기본 연산 : 벡터의 덧셈 & 벡터의 상수배
    - 벡터 x를 *3, *0.5 등 방향은 그대로고 길이를 늘이거나 줄이거나 하는 것을 스케일링이라고 한다. 그리고 상수들은 스칼라라고 지칭한다.


##### 선형 회귀 
```py
from scipy import stats
stats.linregress([1, 3, 5, 7, 9], [2, 8, 14, 20, 26])

#output:
LinregressResult(slope=3.0, intercept=-1.0, rvalue=1.0, pvalue=1.2004217548761408e-30, stderr=0.0)
```
scipy라는 라이브러리에 선형 회귀를 사용할 수 있게 이미 구현되어 있다는 것을 알고 넘어가자.

선형 회귀(by numpy)에 대해 궁금하다면 [이곳](https://woowabros.github.io/study/2018/08/01/linear_regression_qr.html)을 참조하자.


##### Dimensionality Reduction : PCA, SVD 
아마 이번 section에서 가장 중요한 것이 **차원 축소**라고 생각한다.

차원 축소를 하는 가장 간단한 이유는 **계산량**을 줄이기 위한 것으로 생각하면 쉽다. 혹은 사이즈가 큰 데이터 셋을 사이즈가 작은 부분으로 나누는 작업으로 생각하면 된다.


##### [잠깐 쉬는 타임~]
**colab에 library** 추가하는 법!
```py
!pip3 install ~~~ 

ex)
!pip3 install imageio
!pip3 install skimage
!pip3 install scikit-image
```
##### 스칼라?


