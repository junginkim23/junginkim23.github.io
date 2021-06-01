---
title : "[Python] - matplotlib"
category :
    - Python
tag : 
    - plot
    - picture
    - seaborn
    - graph
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

### 시각화 - matplotlib

##### 1. fig size 조절

```py
fig = plt.figure(figsize=(20, 10)) #(가로,세로)
```

##### 2. subplot 

```py
#subplot
ax1 = fig.add_subplot(2,2,1)
ax2 = fig.add_subplot(2,2,2)
ax3 = fig.add_subplot(2,2,3) 
ax4 = fig.add_subplot(2,2,4) 

or

# subplot 생성 및 figure 사이즈 조절 
figure, ((ax1,ax2,ax3), (ax4,ax5,ax6)) = plt.subplots(nrows=2, ncols=3)
figure.set_size_inches(18,8)

#seaborn 이용해서 막대그래프 생성. subplot 지정.
sns.barplot(data=train, x="year", y="count", ax=ax1)
sns.barplot(data=train, x="month", y="count", ax=ax2)
sns.barplot(data=train, x="day", y="count", ax=ax3)
sns.barplot(data=train, x="hour", y="count", ax=ax4)
sns.barplot(data=train, x="minute", y="count", ax=ax5)
sns.barplot(data=train, x="second", y="count", ax=ax6)

#subplot title 부여 
ax1.set(ylabel='Count',title="연도별 대여량")
ax2.set(xlabel='month',title="월별 대여량")
ax3.set(xlabel='day', title="일별 대여량")
ax4.set(xlabel='hour', title="시간별 대여량")
```

##### 3. 선 그래프 

```py
#선 그래프 생성 
plt.plot(x,y,label = '라벨 이름')

#범례 표시
plt.legend()
```