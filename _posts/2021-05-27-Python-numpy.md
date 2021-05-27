---
title : "[Python] - numpy"
category :
    - Python
tag : 
    - Linear Algebra
    - vector 
    - matrix
    - numpy
    - tensor
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

a.reshape(-1)
#output : array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11])
```

##### 행렬곱 dot & matmul
```py
>>> import numpy as np
>>> A = np.arange(2*3*4).reshape((2,3,4))
>>> B = np.arange(2*3*4).reshape((2,4,3))
>>> np.dot(A,B).shape
(2, 3, 2, 3)
>>> np.matmul(A,B).shape
(2, 3, 3)
```
numpy.dot은 두 배열의 내적곱 
numpy.matmul은 두 배열의 행렬곱이라고 하는데, 현재는 이 정도로만 알고 넘어가자. 

좀 더 자세한 내용에 대해서는 [여기](https://m.blog.naver.com/PostView.naver?blogId=cjh226&logNo=221356884894&proxyReferer=https:%2F%2Fwww.google.com%2F)를 참조하면 될 것 같다. 

##### tensor?

matrix와 tensor의 차이를 가볍게 짚고 넘어가보자.

matrix란, 2차원 구조(행과 열)를 갖는 것을 가리키고 tensor란 행렬을 일반화한 것(즉, 3차원/4차원 등으로 확장한 것)을 말한다. 

그래서 행렬곱은 두 행렬을 곱하는 것이고 두 텐서를 곱하는 것을 텐서곱이라고 한다.

##### np.cov & np.corrcoef
```py
# 공분산
np.cov(v, w)
#output: 대각선의 값은 각 feature의 분산이고, 그 외의 값이 공분산 값이 된다.
        v      w
v  1363.7   71.7
w    71.7  149.7

# 상관계수
np.corrcoef(v, w)
#output: [0,1] 해당 인덱스가 두 feature의 상관 계수가 된다.
         v        w
v  1.00000  0.15869
w  0.15869  1.00000
```
##### np.concatenate() & np.stack
```py
a = np.array([[1,2],[2,3]]) #a.shape (2,2)
b = np.array([[3,4]]) #b.shape (1,2)

#concatenate는 합칠 axis의 shape값을 제외하고 나머지 shape 값이 일치하면 두 벡터 값 혹은 행렬 값을 합칠 수 있다.
np.concatenate((a,b),axis=0) #np.concatenate((a,b),axis=0).shape (3,2)
#output : 
array([[1, 2],
       [3, 4],
       [5, 6]])

a = np.array([[1, 2], [3, 4]]) # a.shape=(2, 2)
b = np.array([[5, 6], [7, 8]]) # b.shape=(2, 2)

np.stack((a,b)) #np.stack((a,b)).shape (2,2,2)
#output : 
array([[[1, 2],
        [3, 4]],

       [[5, 6],
        [7, 8]]])
```
##### np.linalg.matrix_rank(array)
```py
array의 rank를 반환해준다.
```