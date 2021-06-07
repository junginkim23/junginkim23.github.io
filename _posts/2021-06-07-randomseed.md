---
title : "[Python] - random seed?"
category :
    - Python
tag : 
    - random seed
    - seed
    - numpy
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

<img src='/assets/python.jpg' width = 1000 height = 800 >

numpy를 이용해서 random한 수를 출력하려 할 때마다 동일한 난수를 생성하기 위해서 **np.random.seed**를 사용해야 한다. 그렇다면 np.random.seed가 무엇인지 **코드를 통해 확인**해보자.

>np.random.seed 사용 x 

```py
for _ in range(3):
    print(np.random.randint(1,10,4))
#output:
[4 4 4 2]
[8 7 8 3]
[4 4 4 1]
```
for문을 통해 3번 출력해보았지만 결과가 매번 다른 것을 확인할 수 있었다. 이번에는 np.random.seed를 사용해보자.

>np.random.seed 사용

```py
for _ in range(3):
  np.random.seed(0)
  print(np.random.randint(1,10,4))
#output:
[6 1 4 4]
[6 1 4 4]
[6 1 4 4]
```

np.random.seed를 사용하니 동일한 난수가 계속 생성된 것을 확인할 수 있었다. 

>그렇다면 np.random.seed의 파라메터인 seed_value는 무엇을 하는 것일까?

seed_value는 유사난수 생성기 **시드**를 만들어 준다. 그래서 난수를 생성할 때에 seed value를 리셋해주면 매 순간 동일한 난수가 선언될 수 있다.

>그럼, seed_Value에는 어떤 값을 넣어주어야 할까? 

seed_value에는 특정한 값을 넣어줄 필요가 없다. 아무 수나 넣어주면 된다. 그럼 그 수를 통해 서로 다른 유사난수 생성기 **시드**를 만들어 줄 뿐이다. 그렇게 되면 해당 seed_value에 해당하는 시드별로 서로 다른 난수를 생성해주게 된다. 코드를 통해 확인해보자. 

```py
for _ in range(2):
    np.random.seed(1)
    print(np.random.randint(1,10,3))
#output:
[6 9 6]
[6 9 6]

for _ in range(2):
    np.random.seed(2)
    print(np.random.randint(1,10,3))
#output:
[9 9 7]
[9 9 7]
```
seed_value의 값만 달리해줬을 뿐인데 다른 난수가 서로 계속 생성된 것을 확인할 수 있었다. 즉 값이 달라지면 그 값에 따라 다른 시드(유사난수 생성기)가 생성되기 때문에 반환값이 달라지게 된다. 