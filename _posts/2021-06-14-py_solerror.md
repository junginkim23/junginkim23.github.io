---
title : "[Python] 최신 버전으로 업데이트하기"
excerpt: "라이브러리의 특정 변수 또는 함수를 사용할 때 version up이 되어 있지 않아 발생하는 오류를 해결해보자."
toc : true 
toc_sticky: true
# author_profile: true
# sidebar:
#   nav: "sidebar-contents"

header:
    teaser: /assets/python.jpg

category :
    - Python
tag : 
    - machine learning
    - error
    - version up

last_modified_at: 2021-06-14T18:30-19:00
---

## 개요
<img src='/assets/python.jpg' width = 1000 height = 800 >

코랩에서 특정 라이브러리 내의 클래스로 만든 객체를 사용해 변수 또는 함수를 호출할 때 버전이 업데이트 되지 않아 에러 메세지를 출력해준다. 

이러한 경우 `!pip install`를 사용해 해당 라이브러리의 버전을 최신 버전으로 업데이트 시켜 문제를 해결할 수 있다.

## 예시

```py
## import OneHotEncoder
from category_encoders import OneHotEncoder

## 원핫 인코딩
encoder = OneHotEncoder(use_cat_names = True)
X_train = encoder.fit_transform(X_train)
X_test = encoder.transform(X_test)
```
<img src='/assets/error.PNG' width = 1000 >

> 해당 문제 해결 

```py
!pip install category_encoders
```
<img src='/assets/solve.PNG' width = 1000 >

**위의 코드로 `category_encoders`를 설치하고 나서 에러가 발생했던 코드를 실행하면 오류가 출력되지 않는 것을 확인할 수 있습니다.**