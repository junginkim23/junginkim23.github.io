---
title : "[Python] Seaborn"
excerpt: "seaborn 라이브러리 활용 시각화"
header:
    teaser: /assets/python.jpg
author_profile: true
sidebar:
  nav: "sidebar-contents"
category :
    - Python
tag : 
    - plot
    - picture
    - seaborn
    - graph
toc : true 
toc_sticky: true
---

<img src='/assets/python.jpg' width = 1000 height = 800 >

### 시각화 - seaborn

[참조1](https://tariat.tistory.com/744) 참고!

[참조2](https://programmers.co.kr/learn/courses/21/lessons/942) 참고!

##### 1. 막대그래프: barplot 

```py
import seaborn as sns 

sns.barplot(data = local_df, x = 'genre',y= value).set_title('NA(2013~2020)')
#output:
```
<img src='/assets/seaborn_ex.PNG' width = 400>




##### 2. 박스플랏 : boxplot 

##### 3. 히스토그램 : histogram

##### 4. 산점도 :scatterplot

##### 5. 라인그래프 : lineplot

 