```python
import pandas as pd
import numpy as np
```


```python
## 1. 2022년 11월 28일부터 12월 5일까지의 데이터를 가진 index를 생성하고 나머지 colunms를 랜덤으로 생성 후 df를 copy해서 0보다 작은 값들은 
##    0으로 바꿔줘라
```


```python
dates = pd.date_range("20221128", periods=8)
dates
```




    DatetimeIndex(['2022-11-28', '2022-11-29', '2022-11-30', '2022-12-01',
                   '2022-12-02', '2022-12-03', '2022-12-04', '2022-12-05'],
                  dtype='datetime64[ns]', freq='D')




```python
df = pd.DataFrame(np.random.randn(8, 4), index=dates, columns=list("ABCD"))
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2022-11-28</th>
      <td>1.437896</td>
      <td>0.151436</td>
      <td>-0.504565</td>
      <td>-1.348828</td>
    </tr>
    <tr>
      <th>2022-11-29</th>
      <td>-0.984035</td>
      <td>-1.654411</td>
      <td>-0.647104</td>
      <td>-0.411081</td>
    </tr>
    <tr>
      <th>2022-11-30</th>
      <td>0.924350</td>
      <td>0.575768</td>
      <td>0.172011</td>
      <td>0.253549</td>
    </tr>
    <tr>
      <th>2022-12-01</th>
      <td>0.273152</td>
      <td>-0.122031</td>
      <td>-0.890127</td>
      <td>-0.900950</td>
    </tr>
    <tr>
      <th>2022-12-02</th>
      <td>0.717110</td>
      <td>-0.373293</td>
      <td>-0.195160</td>
      <td>0.153014</td>
    </tr>
    <tr>
      <th>2022-12-03</th>
      <td>-1.927220</td>
      <td>0.906832</td>
      <td>-0.785202</td>
      <td>0.963147</td>
    </tr>
    <tr>
      <th>2022-12-04</th>
      <td>-0.066144</td>
      <td>-0.338183</td>
      <td>-0.371897</td>
      <td>-0.608714</td>
    </tr>
    <tr>
      <th>2022-12-05</th>
      <td>-0.713754</td>
      <td>0.469627</td>
      <td>2.233176</td>
      <td>0.478393</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = df.copy()
df2[df2 < 0] = 0
df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
      <th>D</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2022-11-28</th>
      <td>1.437896</td>
      <td>0.151436</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>2022-11-29</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>2022-11-30</th>
      <td>0.924350</td>
      <td>0.575768</td>
      <td>0.172011</td>
      <td>0.253549</td>
    </tr>
    <tr>
      <th>2022-12-01</th>
      <td>0.273152</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>2022-12-02</th>
      <td>0.717110</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.153014</td>
    </tr>
    <tr>
      <th>2022-12-03</th>
      <td>0.000000</td>
      <td>0.906832</td>
      <td>0.000000</td>
      <td>0.963147</td>
    </tr>
    <tr>
      <th>2022-12-04</th>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>2022-12-05</th>
      <td>0.000000</td>
      <td>0.469627</td>
      <td>2.233176</td>
      <td>0.478393</td>
    </tr>
  </tbody>
</table>
</div>




```python
## 2. df2의 값 중 A와 B의 2022년 12월 2일 까지의 값만 추출해라
```


```python
df.iloc[0:5, :2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2022-11-28</th>
      <td>1.437896</td>
      <td>0.151436</td>
    </tr>
    <tr>
      <th>2022-11-29</th>
      <td>-0.984035</td>
      <td>-1.654411</td>
    </tr>
    <tr>
      <th>2022-11-30</th>
      <td>0.924350</td>
      <td>0.575768</td>
    </tr>
    <tr>
      <th>2022-12-01</th>
      <td>0.273152</td>
      <td>-0.122031</td>
    </tr>
    <tr>
      <th>2022-12-02</th>
      <td>0.717110</td>
      <td>-0.373293</td>
    </tr>
  </tbody>
</table>
</div>




```python
## 3. Data의 index를 word로 바꾸고 Name의 이름이 Nathan이면 Seed의 값을 가장 높은 값으로 하고 
##   가장 높은 값을 가졌던 Seed의 값을 0으로 바꿔라
```


```python
word = ['a','b', 'c', 'd']
```


```python
Data = pd.DataFrame({'ID': ['Good guy', 'Hair loss', 'Rock', 'Hulk'],
                     'Name':['Nathan', 'Andrew', 'Peter','Jacob'],
                     'Seed':[2000, 198000, 150000, 400000],
                     'Class':['D','c','B','A']})
df3 = pd.DataFrame(Data,columns=['ID','Name','Seed', 'Class'])
```


```python
Data
df3
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Name</th>
      <th>Seed</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Good guy</td>
      <td>Nathan</td>
      <td>2000</td>
      <td>D</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Hair loss</td>
      <td>Andrew</td>
      <td>198000</td>
      <td>c</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Rock</td>
      <td>Peter</td>
      <td>150000</td>
      <td>B</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hulk</td>
      <td>Jacob</td>
      <td>400000</td>
      <td>A</td>
    </tr>
  </tbody>
</table>
</div>




```python
Data.index = word
```


```python
Data
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Name</th>
      <th>seed</th>
      <th>class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>Good guy</td>
      <td>Nathan</td>
      <td>2000</td>
      <td>D</td>
    </tr>
    <tr>
      <th>b</th>
      <td>Hair loss</td>
      <td>Andrew</td>
      <td>198000</td>
      <td>c</td>
    </tr>
    <tr>
      <th>c</th>
      <td>Rock</td>
      <td>Peter</td>
      <td>150000</td>
      <td>B</td>
    </tr>
    <tr>
      <th>d</th>
      <td>Hulk</td>
      <td>Jacob</td>
      <td>400000</td>
      <td>A</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[df['Name'] == 'Nathan', 'Seed'] = 400000
df.loc[df['Name'] == 'Jacob', 'Seed'] = 0
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>ID</th>
      <th>Name</th>
      <th>Seed</th>
      <th>Class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Good guy</td>
      <td>Nathan</td>
      <td>400000</td>
      <td>D</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Hair loss</td>
      <td>Andrew</td>
      <td>198000</td>
      <td>c</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Rock</td>
      <td>Peter</td>
      <td>150000</td>
      <td>B</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Hulk</td>
      <td>Jacob</td>
      <td>0</td>
      <td>A</td>
    </tr>
  </tbody>
</table>
</div>




```python

```
