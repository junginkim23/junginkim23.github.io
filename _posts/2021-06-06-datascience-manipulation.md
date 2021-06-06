---
title : "[Data Science] - Data Manipulation"
category :
    - Data Science 
tag : 
    - EDA
    - Data-Processing
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

### Data Manipulation

<img src='/assets/datascience.png' width = 1000 height = 800 >

#### 개요

- pandas를 통해 데이터를 concat/merge 할 수 있다.
- tidy 데이터에 대한 개념을 이해한다.
- melt와 pivot/pivot_table 함수를 사용하여 wide와 tidy 형태의 데이터를 서로 변환할 수 있다.

##### 1. data 합치기

우리가 효과적인 데이터 분석을 위해서는 데이터를 합치는 것도 필요하다. 그 중에서도 대표적으로 **concat & merge**에 대해 알아보겠다.

##### 1-1. Concat 

**concat**은 '더한다' 혹은 '붙인다'라는 의미로 생각하면 이해가 편리하다. 예를 들어 두 개의 문자열을 '+'을 통해 더할 수 있습니다. 

```py
'hi' + 'hello' #output: hihello
```

**+ 연산자**를 사용하지 않고도 파이썬 내장함수를 통해 문자열을 더할 수 있습니다. 

```py
#join
'_'.join(['a','b']) #output: 'a_b'
```

더하는 것뿐만 문자열을 쪼개는 것도 파이썬의 split() 내장함수를 이용하면 가능합니다. 

split의 parameter로 쪼개는 기준이 되는 인자를 넣어 줍니다.

```py
'hi my name is jungin'.split(' ') 
#output: ['hi', 'my', 'name', 'is', 'jungin']
```
이제 본격적으로 데이터 프레임내의 열 또는 행을 합치는 것을 살펴보겠습니다. 

데이터프레임을 더할 때는 일반적으로 열 또는 행의 이름이나 인덱스가 일치해야 합니다. 그렇지 않은 경우 비어있는 부분에 대해서는 NaN 값으로 채워지게 됩니다. 

```py
import pandas as pd

x = pd.DataFrame([[10,20],[4,8]],index=['A','B'],columns=['X','Y'])
y = pd.DataFrame([[30,10],[5,4]],index=['A','C'],columns=['X','Z'])

pd.concat([x,y],axis=1)
```
<img src='/assets/a.png' width = 300 >

>위의 그림을 보면 x 데이터프레임에는 C라는 index가 없기 때문에 해당 feature에 NaN이 들어갔고 y 데이터프레임에는 B라는 인덱스가 없기 때문에 해당 feature에 NaN 값이 들어간 것을 확인할 수 있다.

