# Python 生成式、生成器与迭代器

## 列表生成式

列表生成式会一次性创建完整列表，因此取值快，但数据量大时会占用更多内存。

```python
letters = [x + y for x in "ABCDE" for y in "123"]
print(letters)

squares = [x ** 2 for x in range(1, 10)]
print(squares)
```

## 生成器表达式

生成器表达式不会一次性保存所有结果，而是在迭代时按需计算。

```python
squares = (x ** 2 for x in range(1, 10))

for value in squares:
    print(value)
```

如果要对比内存占用，可以使用 `sys.getsizeof`：

```python
import sys

list_squares = [x ** 2 for x in range(1, 1000)]
generator_squares = (x ** 2 for x in range(1, 1000))

print(sys.getsizeof(list_squares))
print(sys.getsizeof(generator_squares))
```

## `yield` 生成器函数

函数中出现 `yield` 时，这个函数会返回生成器对象。每次调用 `next()`，代码会运行到下一个 `yield` 并暂停。

```python
def foo():
    print("starting...")
    while True:
        result = yield 4
        print("result:", result)


generator = foo()
print(next(generator))
print("*" * 20)
print(next(generator))
```

输出示例：

```text
starting...
4
********************
result: None
4
```

## 迭代器、生成器和列表的区别

- **列表**：一次性把所有数据放入内存，适合数据量不大、需要反复访问的场景。
- **迭代器**：按需逐个取值，实现了 `__iter__()` 和 `__next__()`。
- **生成器**：一种特殊的迭代器，通常由生成器表达式或包含 `yield` 的函数创建。

## 记忆要点

- 需要立刻得到完整结果时，用列表生成式。
- 数据量大或只需要遍历一次时，优先考虑生成器。
- 生成器节省内存，但每次取值都需要重新进入计算流程。
