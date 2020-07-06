# Python函数的参数传递

## 参数传递机制具有值传递（int、float等值数据类型）和引用传递（以字典、列表等非值对象数据类型为代表）两种基本机制。

### 值传递，应用的参数不发生更改（传了个副本进去）
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

### 引用传递，引用的参数发生更改（传的是真实的地址）
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

## 重点

### Python中还允许包裹方式的参数传递，这为不确定参数个数和参数类型的函数调用提供了基础。

**知识点**

**1.在函数调用时，\*会以单个元素的形式解包一个元祖，使其成为独立的参数。**

**2.在函数调用时，\*\*会以键/值对的形式解包一个字典，使其成为独立的关键字参数。**

```python
def f(a,*args):
    print(args)

f(1,2,3,4)
​```
输出为：(2, 3, 4)
​```
```
虽然传入1,2,3,4，但是解包为（1），（2,3,4），其中a是1，args是剩下的。
```python
def f(a,b,*args):
    print(a)
    print(args)
f([1,2,3,4,5])
​```输出为：
1
(3, 4, 5)   # 变成元组了
​```
```

在Python中，当\*和\*\*符号出现在函数定义的参数中时，表示任意数目参数。\*arg表示任意多个无名参数，类型为tuple;\*\*kwargs表示关键字参数，为dict，使用时需将\*arg放在\*\*kwargs之前，否则会有“SyntaxError: non-keyword arg after keyword arg”的语法错误。

再看看\*\*kwargs的参数传递的例子
```python
def f(**kargs):
    print(kargs)
    
f(a=1,b=2) # 实际传入参数是两个,但是给包裹在一起
​```output:
{'a': 1, 'b': 2}
​```
```
```python
def person(name,age,**kw):
    print('name:',name,'age:',age,'other:',kw)
# 传入4个参数，自动将后两位  拼接到成字典
person('Adam', 45, gender='M', job='Engineer')

​```output
name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}
​```
```

再看看\*args和\*\*kwargs混合的例子
```python
def h(a,*args,**kwargs):
    print(a,args,kwargs)

h(1,2,3,x=4,y=5)
# 丢进去不确定参数的包裹：1,2,3，x=4,y=5
# 解包：1                    -a
# 解包：（2,3）				 -*args
# 解包：{'x': 4, 'y': 5}	  -**kwargs
​```output
1 (2, 3) {'x': 4, 'y': 5}
​```
```
