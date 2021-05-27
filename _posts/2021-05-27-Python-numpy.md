---
title : "[Python] - numpy"
category :
    - Data Science 
tag : 
    - Linear Algebra
    - vector 
    - matrix
    - numpy
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

### numpy의 유용한 메소드

##### np.ones
```py
np.ones(5) #output: [1.0,1.0,1.0,1.0,1.0]
```

##### reshape 메소드

배열과 차원을 변형해주는 함수이다.
**np.reshape(변경할 배열, 차원)** or **배열.reshape(차원)**으로 사용할 수 있다.
```py
df['final'].values.reshape(-1,1).shape #output : (5,1)
df['final'].shape #output : (5,)

df['final'].values
df['final'].values.reshape(-1,1)

#output
array([ 2,  8, 14, 20, 26])

#output
array([[ 2],
       [ 8],
       [14],
       [20],
       [26]])
```

reshape을 활용하다 보면 입력인수로 -1이 입력되는 것을 볼 수 있다.
-1의 의미는 변경된 배열의 -1의 위치의 차원은 '원래 배열의 길이와 다른 입력 인수로부터 결정된다. 

다음의 코드를 보고 이해를 해보자. 

```py
a = np.arange(12) 
#output : array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11])

a.reshape(3,4)
#output : 
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])

a.reshape(3,-1)
#output : 
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])

a.reshape(-1,2)
#output :
array([[ 0,  1],
       [ 2,  3],
       [ 4,  5],
       [ 6,  7],
       [ 8,  9],
       [10, 11]])
```