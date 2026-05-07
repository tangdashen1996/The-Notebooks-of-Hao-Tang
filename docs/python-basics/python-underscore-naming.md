# Python 下划线命名约定

Python 中的下划线既可能是命名约定，也可能触发解释器行为。下面按常见形式汇总。

| 模式 | 示例 | 含义 |
| --- | --- | --- |
| 单前导下划线 | `_var` | 约定为“内部使用”。通常不由解释器强制限制，但 `from module import *` 默认不会导入这类名称。 |
| 单末尾下划线 | `var_` | 用于避免与 Python 关键字或内置名称冲突，例如 `class_`。 |
| 双前导下划线 | `__var` | 在类作用域中触发名称修饰（name mangling），用于降低子类误覆盖属性的概率。 |
| 双前导和双末尾下划线 | `__var__` | Python 语言定义的特殊方法或属性，例如 `__init__`、`__name__`。不要随意自造这类名称。 |
| 单下划线 | `_` | 常用作临时变量、无意义变量；在 Python REPL 中也表示最近一次表达式的结果。 |

## 示例

```python
class Example:
    def __init__(self):
        self._internal = "内部约定"
        self.class_ = "避免关键字冲突"
        self.__private = "触发名称修饰"

obj = Example()
print(obj._internal)
print(obj.class_)
print(obj._Example__private)
```

## 记忆要点

- 单下划线多数是“给人看的约定”。
- 双前导下划线在类中会影响实际属性名。
- 双前后下划线是 Python 自身协议的一部分，日常命名应避免滥用。
