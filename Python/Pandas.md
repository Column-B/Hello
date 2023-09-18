판다스는 Python의 데이터 분석 라이브러리이다. R에서 사용되던 `data.frame`구조를 본뜬 `DataFrame`이라는 구조를 사용한다. 파이썬이라는 접근성이 좋은 언어 기반으로 동작하기 때문에 데이터 분석을 파이썬으로 입문하는 사람들이 필수적으로 사용하는 라이브러리가 되었다. 주요 코드는 Python이나 C로 작성되었다.

<h6>Import</h6>
```python
import pandas as pd
```

<h6>Series, DataFrame</h6>
![[Pasted image 20230917153841.png]]
`Series`는 [[NumPy]]에서 제공하는 1차원 배열과 비슷하지만, 각 데이터의 의미를 표시하는 `index`를 붙일 수 있다. 데이터 자체는 `value`라고 한다.

`DataFrame`은 `Series`들을 하나의 열로 취급한 집합이다. 2차원 행렬 데이터에 `index`를 붙인 것과 같다. `row index`, `column index`가 있다. 데이터를 표의 형태로 처리한다. RDB 환경에서 SQL로 테이블을 컨트롤할 수 있는 수준의 기능들이 상당 부분 구현되있다.

ndarray는 하나의 data type을 가진다. 즉, List와 달리 Dynamic typing이 지원되지 않는다.

판다스의 큰 장점인 라벨링을 활용할 수 있다.

```python
df = pd.DataFrame([[3, 2, 5], [10, 0 ,2], [6, 5, 3]], index = ["이성계", "김유신", "이순신"], columns=["사과", "자두", "포도"])
s1 = df["사과"]
```

`NumPy`기반으로 제작되었기 때문에 `df.mean()`, `df1.sum()`등을 사용 가능하다.

<h6>Indexing, Slicing</h6>
![[Pasted image 20230917154532.png]]
기존의 Python과 비슷하다.
```python
df[] -> [] columns 추출..
df.loc[index 이름, columns 이름] # 이름
df.iloc[index 번호, columns 번호] # 번호
df.drop("D", axis=1) # Default = 0
```
![[Pasted image 20230917154834.png]]
axis는 이를 참조하면 된다.

만약 B, D, E, F 열과 가, 나, 다 행을 추출하고 싶다면.. (A ~ F 열, 가 ~ 마 행의 데이터)
```python
df.iloc[:3, 1:].drop("C", axis=1)
```

<h6>Sorting</h6>
`sort_values`로 값을 기준으로 정렬할 수 있다. `ascending`이 True일 때 오름차순으로 정렬한다.
```python
df.sort_values(["수학", "나이"], ascending=[0,1])
```

<h6>Broadcasting</h6>
`Broadcasting`은 기본적으로 `NumPy`의 `Broadcasting`과 비슷하다. 그러나 몇 가지 차이점이 있다. `Pandas`에서는 라벨링이 중요하다. 라벨이 맞지 않으면 없는 부분으로 `NaN`값을 채운다.

`DataFrame`과 `Series`의 연산을 `Broadcasting`이라 칭할 수 있다.

<h6>Boolean Indexing</h6>
`bool` 자료형을 이용하여 인덱싱을 활용하는 기법.
