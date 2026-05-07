# Python 正则表达式参考

正则表达式用于描述字符串匹配规则，常用于搜索、校验、替换和提取文本。

## 学习建议

建议按以下顺序学习：

1. 普通字符与元字符，例如 `.`, `^`, `$`, `*`, `+`, `?`。
2. 字符集合，例如 `[abc]`, `[^abc]`, `[a-z]`。
3. 数量词，例如 `{m}`, `{m,n}`。
4. 分组与捕获，例如 `(pattern)`。
5. 常用 Python API，例如 `re.search`, `re.match`, `re.findall`, `re.sub`。

## Python 简单示例

```python
import re

text = "Email: hao@example.com"
match = re.search(r"[\w.-]+@[\w.-]+", text)

if match:
    print(match.group())
```

输出：

```text
hao@example.com
```

## 延伸阅读

- [正则表达式 30 分钟入门教程](https://deerchao.cn/tutorials/regex/regex.htm)
