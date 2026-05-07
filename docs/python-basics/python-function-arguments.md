# Python 函数参数传递、`*args` 与 `**kwargs`

## 参数传递的核心理解

Python 的参数传递常被描述为“对象引用传递”：函数接收到的是对象引用。对象是否会被函数修改，取决于对象本身是否可变，以及函数内部做的是“修改对象”还是“重新绑定变量名”。

## 不可变对象：函数内重新绑定不影响外部变量

```python
a = 5


def test(value):
    value += 1
    print("函数内：", value)


print(a)
test(a)
print(a)
```

输出：

```text
5
函数内： 6
5
```

这里的 `value += 1` 会让局部变量 `value` 绑定到新的整数对象，不会改变外部的 `a`。

## 可变对象：函数内修改对象会影响外部变量

```python
a = [1, 2, 3]


def test(values):
    values.append(4)
    print("函数内：", values)


print(a)
test(a)
print(a)
```

输出：

```text
[1, 2, 3]
函数内： [1, 2, 3, 4]
[1, 2, 3, 4]
```

这里 `append` 修改的是同一个列表对象，因此外部变量也能看到变化。

## `*args`：接收任意数量的位置参数

在函数定义中，`*args` 会把多余的位置参数打包成元组。

```python
def f(a, *args):
    print(a)
    print(args)


f(1, 2, 3, 4)
```

输出：

```text
1
(2, 3, 4)
```

## `**kwargs`：接收任意数量的关键字参数

在函数定义中，`**kwargs` 会把多余的关键字参数打包成字典。

```python
def person(name, age, **kwargs):
    print("name:", name, "age:", age, "other:", kwargs)


person("Adam", 45, gender="M", job="Engineer")
```

输出：

```text
name: Adam age: 45 other: {'gender': 'M', 'job': 'Engineer'}
```

## 混合使用

常见顺序是：普通参数、`*args`、默认参数、`**kwargs`。

```python
def h(a, *args, **kwargs):
    print(a, args, kwargs)


h(1, 2, 3, x=4, y=5)
```

输出：

```text
1 (2, 3) {'x': 4, 'y': 5}
```

## 调用函数时的解包

调用函数时，`*` 可以解包序列，`**` 可以解包字典。

```python
def add(a, b, c):
    return a + b + c


numbers = [1, 2, 3]
options = {"a": 1, "b": 2, "c": 3}

print(add(*numbers))
print(add(**options))
```

输出：

```text
6
6
```

## 记忆要点

- `*args` 得到元组，`**kwargs` 得到字典。
- 函数定义中，`*args` 必须放在 `**kwargs` 前面。
- 可变对象作为参数时，要留意函数内部是否会原地修改它。
