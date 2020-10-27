# 生成式和生成器

我们还可以使用列表的生成式语法来创建列表，代码如下所示。
```python
f = [x for x in range(1, 10)]
print(f)
f = [x + y for x in 'ABCDE' for y in '1234567']
print(f)
# 用列表的生成表达式语法创建列表容器
# 用这种语法创建列表之后元素已经准备就绪所以需要耗费较多的内存空间
f = [x ** 2 for x in range(1, 1000)]
print(sys.getsizeof(f))  # 查看对象占用内存的字节数
print(f)
# 请注意下面的代码创建的不是一个列表而是一个生成器对象
# 通过生成器可以获取到数据但它不占用额外的空间存储数据
# 每次需要数据的时候就通过内部的运算得到数据(需要花费额外的时间)
f = (x ** 2 for x in range(1, 1000))
print(sys.getsizeof(f))  # 相比生成式生成器不占用存储数据的空间
print(f)
for val in f:
    print(val)
```

下面代码展示了yield的用法。
```python
def foo():
    print("starting...")
    while True:
        res = yield 4
        print("res:",res)
g = foo()
print(next(g))
print("*"*20)
print(next(g))
```
```python
starting...
4
********************
res: None
4
```

# 关于迭代器和生成器的区别
生成器是一种特殊的迭代器，生成器实现了`迭代器协议--iter--,--next--`。
生成器是可以改变迭代的值的，然而迭代器随意改值会有问题。

# 关于迭代器和list的区别
list直接把所有数据加载到内存。
而迭代器是一个一个取值，在需要下一个值的时候才回去计算取出这个值到内存（可以把迭代器想象成一个生成器的代码，一次next，运行下面的代码，然后返回值）。
