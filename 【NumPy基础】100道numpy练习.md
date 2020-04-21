## 【NumPy基础】100道numpy练习

### 一、初学者10道

1、在python环境中导入numpy包，并命名为np

```python
import numoy as np
```

2、查看numpy版本和配置信息

```python
print(np.__version__)
print(np.__config__.show())
```

3、创建零向量，zeros函数

```python
a = np.zeros((4,4))
a
```

4、将上面的零向量的第二行第三列元素置为1。注意python中行列下标是从0开始。

```python
a[1,2] = 1
a
```

5、arange函数，创建一个在给定范围的向量。

```python
arr = np.arange(10)
```

6、reshape函数，将array变形为矩阵

```python
arr.reshape((2,5))
```

7、nonzero函数，寻找非0元素的下标

```python
index = np.nonzero(a)
```

8、eye函数，生成单位向量

```python
b = np.eye(4)
```

9、diag函数，diagonal对角线。

```python
np.diag(b)
```

10、random模块的random函数，生成随机数

```python
np.random.randn(10)
```

## 二、入门级10道

1、创建一个8*8的“棋盘”矩阵。

```python
np.ones((8,8))
```

2、min()、max()函数

```python
a = np.arange(10).reshape(2,5)
print(a)
print(a.min(axis = 1))
print(a.max(axis = 0))
```

3、函数tile(A,reps),reps即重复的次数，不仅可以是数字，还可以是array。比如构造棋盘矩阵：

```python
np.tile(np.ones((3,1)),3)
```

4、归一化，将矩阵规格化到0～1，即最小的变成0，最大的变成1，最小与最大之间的等比缩放。

```python
b = np.random.random(10)
print(b)
b_stand = (b - b.min())/(b.max() - b.min())
b_stand
```

5、矩阵点乘

```python
arr1 = np.random.random((2,4))
print(arr1)
arr2 = np.arange(8).reshape(2,4)
arr1*arr2
```

6、矩阵相加，5x5矩阵+1x5的向量，相当于每一行都加上1x5矩阵

```python
arr1 = np.random.random((5,5))
print(arr1)
arr2 = np.arange(5).reshape(1,5)
arr1+arr2
```

7、linspace函数，在给定区间中生成均匀分布的给定个数。函数原型 linspace(start, stop, num=50, endpoint=True, retstep=False)

```python
np.linspace(0,1,num=20)
```

8、sort函数。调用random模块中的random函数生成10个随机数，然后sort排序。

```python
num = np.random.random(10)
print(num)
np.sort(num)
```

9、allclose函数，判断两个array在误差范围内是否相等
函数原型allclose(a, b, rtol=1e-05, atol=1e-08)，若absolute(a - b) <= (atol + rtol * absolute(b))则相等。

```python
a = np.random.random(1)
b = np.random.random(1)
np.allclose(a,b,atol=1e-6,rtol=1e-4)
```

10、mean函数，求平均值

```python
a = np.random.random((5,3))
print(a)
print(np.mean(a,axis=0))
print(np.mean(a,axis=1))
```