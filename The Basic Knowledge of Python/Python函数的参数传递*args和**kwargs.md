# 参数传递机制具有值传递（int、float等值数据类型）和引用传递（以字典、列表等非值对象数据类型为代表）两种基本机制。

## 值传递，应用的参数不发生更改（传了个副本进去）
```python
a = 5
print(a)
def test(a):
    a+=1
    print("函数内：%d" % a)
test(a)
print(a)
​```output
5
函数内：6
5
​```
```

## 引用传递，引用的参数发生更改（传的是真实的地址）
```python
a = [1,2,3]
print(a)
def test(a):
    a.append(4)
    print("函数内:",a)
test(a)
print(a)
​```
[1, 2, 3]
函数内: [1, 2, 3, 4]
[1, 2, 3, 4]
​```
```
