Numarray와 Numeric이라는 오래된 Python 패키지를 계승해서 나온 수학 및 과학 연산을 위한 파이썬 패키지이다. Py는 파이썬을 나타내기 때문에, 일반적으로 넘파이라고 읽는다.

장점으로는
* NumPy 내부는 C, 포트란으로 작성되어 있어 상당히 빠른 편이다. 일반 파이썬의 리스트에 비해 메모리를 효율적으로 사용한다.
* 선형 대수 계산에 유리하다.
* 반복문을 지양한다.

<h6>Import</h6>
```python
import numpy as np
```

<h6>ndaray</h6>
NumPy의 배열 class는 `ndarray`이다. NumPy의 주요 객체는 the homogeneous multidimensional 배열이다.

ndarray는 하나의 data type을 가진다. 즉, List와 달리 Dynamic typing이 지원되지 않는다.

![[Pasted image 20230917145136.png]]

```python
test_array = np.array([1, 4, 5, 8])
```

<h6>ndarray.ndim</h6>
배열의 차원을 반환한다.

```python
test_array.ndim
>>> 1
```

<h6>ndarray.shape</h6>
Object의 차원 구성을 tuple 형태로 반환한다. _n_ rows와 _m_ columns이 있다고 해보자, `shape` 는 `(n,m)`이 될 것이다. tuple의 길이는 axis의 개수이다.

```python
test_array.shape
>>> (4,)

matrix = [[1,2,5,8],
         [1,2,5,8],
         [1,2,5,8]]
np.array(matrix, int).shape
>>> (3, 4)
```

<h6>ndarray.size</h6>
배열 요소의 개수

```python
np.array(matrix, int).size
>>> 12
```

<h6>ndarray.dtype</h6>
배열의 요소들의 `datatype`을 나타낸다. `int32`, `int64`, `float64`등의 예시가 있다.

```python
test_array.dtype
>>> dtype('int32')
```

<h6>ndarray.reshape</h6>
데이터의 구조를 바꿔서 처리할 때 `reshape`를 많이 사용한다. 데이터의 개수와 형태의 크기는 같아야 한다. `reshape(n, -1)`를 이용하면 알아서 n의 크기에 맞추어 형태를 정해준다.


```python
test_matrix = [[1,2,3,4], [1,2,5,8]]
np.array(test_matrix).reshape(8,)
>>> array([1, 2, 3, 4, 1, 2, 5, 8])

np.array(test_matrix).reshape(-1,2).shape
>>> (4, 2)

np.array(test_matrix).reshape(2,2,2)
>>> array([[[1, 2],
        [3, 4]],

       [[1, 2],
        [5, 8]]])
```

<h6>ndarray.flatten</h6>
다차원의 `array`를 1차원 `array`로 변환한다.

```python
test_matrix = [[1,2,3,4], [1,2,5,8]]
np.array(test_matrix).flatten()
>>> array([1, 2, 3, 4, 1, 2, 5, 8])
```

<h6>np.arange</h6>
`range`함수처럼 특정 수열을 만들려고 할 때, `ndarray`함수를 이용한다. `range`함수 사용법과 동일하다. `ndarray.arange(시작점, 끝점, step size)`

```python
np.arange(0, 5, 0.5)
>>> array([0. , 0.5, 1. , 1.5, 2. , 2.5, 3. , 3.5, 4. , 4.5])
```

<h6>np.zeros, np.ones, np.empty</h6>
`zeros`는 0으로 가득찬 `array`를 생성한다. `ones`는 1로 가득찬 `array`를 생성한다. `empty`는 비어있는 값으로 이루어진 `array`를 생성한다. (초기화 X)

```python
np.zeros((10,), dtype=np.int8)
>>> array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0], dtype=int8)

np.ones((10,), dtype=np.int8)
>>> array([1, 1, 1, 1, 1, 1, 1, 1, 1, 1], dtype=int8)

np.empty((10,), dtype=np.int8)
>>> array([109,   0, 105,   0, 110,   0, 103,   0,   0,   0], dtype=int8)
```

<h6>something_like</h6>
`_like`는 지정된 `array`의 `shape`의 크기만큼 지정된 값으로 채운다.

```python
test_matrix = np.arange(30).reshape(5, 6)
np.ones_like(test_matrix)
>>> array([[1, 1, 1, 1, 1, 1],
	       [1, 1, 1, 1, 1, 1],
	       [1, 1, 1, 1, 1, 1],
	       [1, 1, 1, 1, 1, 1],
	       [1, 1, 1, 1, 1, 1]])
```

<h6>np.identity</h6>
단위 행렬을 생성한다.

```python
np.identity(3, dtype=np.int8)
>>> array([[1, 0, 0],
	       [0, 1, 0],
	       [0, 0, 1]], dtype=int8)
```

<h6>np.eye</h6>
대각선이 1인 `array`를 생성한다. k값으로 시작 `index`를 변경 가능하다.

```python
np.eye(3, 5, k=2, dtype=np.int8)
>>> array([[0, 0, 1, 0, 0],
	       [0, 0, 0, 1, 0],
	       [0, 0, 0, 0, 1]], dtype=int8)
```

<h6>np.diag</h6>
대각 행렬의 값을 추출한다. 마찬가지로, k값으로 시작 `index`를 변경 가능하다.

```python
matrix = np.arange(9).reshape(3, 3)
print(matrix)
np.diag(matrix)
>>> [[0 1 2]
	 [3 4 5]
	 [6 7 8]]
	array([0, 4, 8])
```

<h6>Random Sampling</h6>
무작위 표본 추출이 가능하다.

```python
np.random.uniform(0, 1, 10).reshape(2, 5) # 균등분포
np.random.normal(0, 1, 10).reshape(2, 5) # 정규분포
```
