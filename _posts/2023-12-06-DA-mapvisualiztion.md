---
title: "[GeoPandas] 파이썬 지도 시각화"
categories:
  - Data Ananlytics
# tags:
comment: true
sidebar:
  nav: "docs"
---

### Introduction
--- 
최근 프로젝트에서 지도 시각화가 필요했었다.
사실 이전에 folium 몇 번 돌려본 경험이 다였기 때문에 매우 걱정이 많았다. 
folium은 코드 자체는 편하지만, 메모리를 많이 사용하는 건지 시간이 비교적 오래걸리는 단점이 있다. (확실하진 않지만, 사용하던 서버에선 그랬다. 그리고 별로 예쁘지 않음)
결국 여기저기 조언을 구해서 Geopandas를 사용해보기로 했는데,,, 행정동 기준이 매우 많고 다양해서 가지고 있는 데이터와 일치하는 shape 데이터를 찾는 것이 매우 힘들었다. 

심지어 가장 많이 사용되었던 데이터는 법정동 기준이라 보유하고 있는 데이터와 맞지 않았다.
법정동-행정동 매핑 데이터도 보유하고 있었으나 안타깝게도 맞지 않았다.
같은 시점 기준 데이터임에도 불구하고 매핑되지 않는 행정동/법정동 명 및 코드들이 매우 많다는 것을 알게 되었다.
많은 분들이 github 이나 여러 블로그에 공유해주셨지만 결국 맞는 것은 없었다.


결국에는 안맞는 행정동들은 수기로 수정했다.
친구한테 물어봤을 때는 Qgis를 활용해서 데이터 추출하는 방법도 있다고 했지만, gis에 대해 아는 것이 없어서 일단 수기로 수정을 하게 되었다. 추후에는 Qgis 사용법을 좀 익히는 게 좋을 것 같다.

  
<br><br>

### 행정동 단위 폴리곤 데이터 수집
--- 

국내 시/도, 시/군/구, 법정동 단위의 shape 데이터는 많은 버전으로 공개되어 있다. 
<br>
[법정동 최신 행정구역(SHP)](http://www.gisdeveloper.co.kr/?p=2332)
<br><br>
추가로, 행정동 단위 데이터도 통계청에서 제공하고 있다. <br>
[통계청 행정동 경계](http://data.nsdi.go.kr/dataset/20171206ds00001)

위 데이터들을 다운받아 압축 해제 후, 사용하면 된다.

(압축폴더 내 파일은 항상 같이 존재해야 함. shp 파일만 빼서 사용하는 것이 불가능함.)

분석 데이터가 행정동 단위였기 때문에 나는 아래 행정동 버전을 사용했다.

<br><br>

### SHP 데이터 로드
--- 

```python
import pandas as pd
import geopandas as gpd

shp = 'Z_SOP_BND_ADM_DONG_PG.shp' 
p1 = gpd.read_file(shp, encoding='cp949')
p1.head()
```

![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/fb84f58e-9268-4ee2-9115-f6fa0b813e33)


geopandas를 호출한다. 시각화는 꼭 geopandas 형태인 채로 해야한다. 데이터 프레임으로 읽고 geopandas로 변환해도 되긴 함.  

<br><br>


### 시각화
---
바로 plot을 때려버리면 이렇게 나온다.
```python
import matplotlib.pyplot as plt

fig, ax = plt.subplots(1, figsize=(20, 20))

d2.plot( cmap='Blues', linewidth=0.8, ax=ax, edgecolor='0.8')
plt.show()
```
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/a35d8074-15a1-409d-a1fb-cbb4f85b7920)
<br><br>
전국 행정동이여서 figsize를 크게 주어야하는 것 같다. 회색으로 보이는 부분은 행정동이 밀집된 부분일 수도 있고, 누락된 데이터일 수도 있다. 



참고로, 나는 수도권 지역만 필요했기 때문에 분리해서 시각화하였다. 

행정동코드는 다행히 비교적 유사해서 앞 두자리가 시/도를 의미하고 있었다. 그러나, 실제 행정동 코드와는 다름.

```python
# 서울특별시
sl = d2[d2['SIG_CD'].str.startswith('11')]
# 경기도
gg = d2[d2['SIG_CD'].str.startswith('41')]
# 인천광역시
ic = d2[d2['SIG_CD'].str.startswith('28')]
```

행정동 앞 두자리로 서울/경기/인천 지역을 구분하였다.

각각을 개별로 시각화 하면 아래와 같다.

cmap을 설정해서 색상도 변경할 수 있다.


```python
fig, ax = plt.subplots(1, figsize=(10, 6))

sl.plot( cmap='Grees', linewidth=0.8, ax=ax, edgecolor='0.8')
plt.show()
```
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/7e2ad220-daca-4e0d-ba35-236258fc6627)

```python
fig, ax = plt.subplots(1, figsize=(10, 6))

gg.plot(cmap='Blues', linewidth=0.8, ax=ax, edgecolor='0.8')
```
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/b465e24b-a05f-4040-93ed-58635f7a646f)

```python
fig, ax = plt.subplots(1, figsize=(10, 6))

ic.plot( cmap='Blues', linewidth=0.8, ax=ax, edgecolor='0.8')
plt.show()
```
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/4e40de38-fbe6-43a5-81bb-861d0d202dd9)





실제 데이터를 활용해서 시각화 할 때는 범례를 추가하거나 축 좌표를 제거하는게 좋은데, 설정은 아래와 같이 하면 된다.

```python
fig, ax = plt.subplots(1, figsize=(10, 6))
ax.axis('off') # 축 제거
sl2.plot(column='data', # 시각화 대상 데이터
            legend=True, # 범례
            cmap='Blues', # 색
            linewidth=0.8, # 테두리 굵기
            ax=ax, # 축
            edgecolor='0.8', # 테두리 색(밝기)
            legend_kwds={'shrink': 0.5}) # 범례 크기
# plt.savefig('./data.png') # 결과 png로 저장
plt.show()
```
![image](https://github.com/MIMjae/MIMjae.github.io/assets/84848848/b473ab4f-14f5-4145-b1b7-68512489d644)


결과는 이런식으로 나온다.

참고로 위 데이터는 가짜 데이터임.

<br>




### References
--- 
[[Geopandas] Python을 이용한 지도 데이터 시각화](!https://yoonseul.tistory.com/8)

[[GeoPandas] 파이썬 지도 시각화](https://f7project.tistory.com/425)


<br><br>
