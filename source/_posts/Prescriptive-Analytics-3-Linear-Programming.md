---
title: "3 Linear Programming"

date: 2023-03-07

tags: [DS]

categories: "Prescriptive Analytics"

cover_image: https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/202303070237.png
---

# **1 Linear Programming**

Linear programming (LP, also called linear optimization) is a method to achieve the best outcome (such as maximum profit or lowest cost) in a mathematical model whose requirements are represented by linear relationships.

Linear programming is a technique for the optimization of a linear objective function, subject to linear equality and linear inequality constraints.

Linear programs are problems that can be expressed in canonical form

* Find a vector $x$
* That maximizes $c^Tx$
* Subject to $Ax \leq b$
* And $x\geq0$

Linear programming is used in business and industry in

* Production planning, 
* transportation and 
* Routing, and 
* Various types of scheduling
* Airlines use linear programs to schedule their flights, considering both scheduling aircraft and scheduling staff

# **2 Optimization Problem**

$$
\begin{align}
Maximize :& 10 x_1+5x_2\\
Constraints :& 5x_1+x_2 \leq90\\
& x_1+10x_2\leq300\\
& 4x_1+6x_2 \leq 125\\
& x_1, x_2 \geq 0
\end{align}
$$

![image-20230307093829700](https://raw.githubusercontent.com/Jiayi-Zeng/Jiayi-Zeng.github.io/pic/img/image-20230307093829700.png)

## 2.1 PuLP Package

```python
from pulp import *
```

**Define variables**

```python
lp = LpProblem("Bakery_Problem", LpMaximize)
x1 = LpVariable(name="Bowdoin_log", lowBound=0)
x2 = LpVariable(name="Chocolate_cake", lowBound=0)
```

**Add the objective function**

```python
lp += 10 * x1 + 5 * x2
print(lp.objective)
```

```
10*Bowdoin_log + 5*Chocolate_cake
```

**Add the constraints**

```python
lp += (5 * x1 + x2 <= 90, "oven")
lp += (x1 + 10* x2 <= 300, "food_processor")
lp += (4 * x1 + 6 * x2 <= 125, "boiler")
```

**Solve the LP**

```python
status = lp.solve()
```

**Print solution**

```py
for var in lp.variables():
  print(var, "=", value(var))
print("OPT=", value(lp.objective))
```

**Output:**

```
Bowdoin_log = 15.961538
Chocolate_cake = 10.192308
OPT= 210.57691999999997
```

