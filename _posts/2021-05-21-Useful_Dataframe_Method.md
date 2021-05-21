---
title : "Useful Dataframe Method"
category :
    - Data Science 
tag : 
    - Pandas
author_profile : true
sidebar_main : False  
toc : true 
use_math: true
---

**Useful Dataframe Method**

**1. data indexing (iloc)**

```py
#읽어온 데이터프레임에서 column 특정 범위만 가지고 온다.
data1 = pd.read_csv(url1).iloc[:,1:]

#또 다른 방법 
data1 = data1.drop(data1.columns[0],axis=1)
```

**2. Add index's name** 

```py
df.rename_axis('추가하고 싶은 명')
```

**3. 데이터 프레임 내 특정 컬럼의 특정 데이터 값만을 뽑고 싶은 경우**

```py
#loc을 사용해 country 컬럼에서 united states와 china의 특정 값만을 추출
df_join = join_data.loc[(join_data['country']=='United States') | (join_data['country']=='China')]

#concat을 사용해 country 컬럼에서 united states와 china의 특정 값만을 추출
usa_china_data = pd.concat([join_data[join_data['country'] == 'United States'],join_data[join_data['country'] == 'China']],axis=0)
```

**4. dataframe 정렬 방법**

```py
#인덱스를 기준으로 오름차순으로 정렬된다.
df = df.sort_index() 
df = df.sort_index(ascending = False) #내림차순으로 정렬

#특정 컬럼을 기준으로 정렬
df = df.sort_values()
df = df.sort_values(ascending = False)#내림차순으로 정렬
```

**5. df.dropna(how='any' or 'all')**

```py
df.dropna(how='any')
  - 만약 na가 존재하면, axis=0 or 1에 따라 해당 행이나 열 삭제!

df.dropna(how='all')
  - 만약 지정된 행이나 열(axis=0 or 1)에 모든 값이 na일때 그 행 or 열 삭제!
```

**6.iloc & loc을 사용해야 하는 이유**

```py
#아래와 같이 인덱싱을 하게 되면 경고 메세지가 뜨는데,
join_data[join_data['time']==2019][join_data['country']=='South Korea']['PPP']

/usr/local/lib/python3.7/dist-packages/ipykernel_launcher.py:2: UserWarning: Boolean Series key will be reindexed to match DataFrame index.

#이러한 경고 메세지를 안 받기 위해서는 iloc이나 loc을 사용해서 인덱싱을 해줘야 한다.
```