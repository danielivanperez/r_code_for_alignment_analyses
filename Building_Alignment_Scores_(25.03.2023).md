```python
import pandas as pd 

df = pd.read_csv("https://raw.githubusercontent.com/danielivanperez/pre_reg_replication_study2_children_adults/main/study_2_children_adult_alignment_(06.12.2022).csv")
```


```python
cv1_children = df.iloc[:42:, 10]
```


```python
# leave-one-out approach code
dic_cv1_children = (cv1_children.value_counts() - 1)/ (sum(cv1_children.value_counts())-1) # eliminando una respuesta "leave-one-out approach"
dic_cv1_children 
```




    a    0.390244
    c    0.243902
    d    0.170732
    b    0.121951
    Name: cv_1, dtype: float64




```python
# building a column with the alignment scores for each child participant
df["align_score_cv1_children"] = cv1_children.replace(pd.Series(dic_cv1_children))
df["align_score_cv1_children"]
```




    0     0.390244
    1     0.390244
    2     0.121951
    3     0.390244
    4     0.390244
            ...   
    61         NaN
    62         NaN
    63         NaN
    64         NaN
    65         NaN
    Name: align_score_cv1_children, Length: 66, dtype: float64




```python
cv1_adults = df.iloc[42:, 10]
```


```python
# leave-one-out approach code
dic_cv1_adults = (cv1_adults.value_counts() - 1)/ (sum(cv1_adults.value_counts())-1) # eliminando una respuesta "leave-one-out approach"
dic_cv1_adults
```




    a    0.608696
    c    0.217391
    b    0.043478
    d    0.000000
    Name: cv_1, dtype: float64




```python
# building a column with the alignment scores for each adult participant
df["align_score_cv1_adults"] = cv1_adults.replace(pd.Series(dic_cv1_adults))
df["align_score_cv1_adults"]
```




    0          NaN
    1          NaN
    2          NaN
    3          NaN
    4          NaN
            ...   
    61    0.608696
    62    0.608696
    63    0.043478
    64    0.217391
    65    0.217391
    Name: align_score_cv1_adults, Length: 66, dtype: float64




```python

```
