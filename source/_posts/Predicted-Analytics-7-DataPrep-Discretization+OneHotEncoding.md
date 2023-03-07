---
title: "9 Data Prep: Discretization & 1Hot Encoding"

date: 2023-02-28

tags: [DS, Data Mining]

categories: "Predicted Analytics: Tools & Techniques"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303060126%20(6).png

---

![image-20230307140225758](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307140225758.png)

# **Discretization**

Converting Numeric Data into Categorical Data

**How to determine the boundaries between classes?**

* Natural boundaries

![image-20230307140432485](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307140432485.png)

* Equi-width ranges

![image-20230307140445235](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307140445235.png)

* Equi-log ranges

![image-20230307140458116](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307140458116.png)

* Equi-depth ranges
  ​		Range [a,b] is chosen
  * Each range has an equal number of records
  * First sort the data
    * Select the boundaries from the sorted 
      data such that each range contains equal number of observations


## Example

**Read Datafile**

```python
import pandas as pd
df = pd.read_csv('Lung Capacity.csv')
```

**Discretize Height into 6 Categories : Width Size is Different**

```python
bins = [0, 50, 55, 60, 65, 70, 100]
group_names = ['A', 'B', 'C', 'D', 'E', 'F']

c1 = pd.cut(df['height'], bins, labels=group_names)
```

# One Hot Encoding

Label Encoder

* Converts Categorical variable into Numerical values
* Starting from 0,1,2,...
* Code is assigned by alphabetical order

## Example

**Load the libraries**

```python
import numpy as np
import pandas as pd

from sklearn import datasets
```

**Read the Dataset**

```python
iris = datasets.load_iris()
print(type(iris))
features = iris["data"]
print(type(features))
print(features[:5,:])

#############################################
print('---------------------------')
labels = iris["target"]
print(type(labels))
print(labels)
```

**Encode the response variable (labels - species) data into one-hot**

```py
labels_onehot_dataframe = pd.get_dummies(labels,prefix='species')
one_hot = np.array(labels_onehot_dataframe)
```

