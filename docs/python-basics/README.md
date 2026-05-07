# Python 基础笔记索引

本目录收录 Python 入门与日常开发中容易混淆的基础知识点。笔记已按主题拆分，适合按需查阅。

## 推荐阅读顺序

| 顺序 | 主题 | 笔记 | 适合解决的问题 |
| --- | --- | --- | --- |
| 1 | 字符串 | [字符串与转义](python-strings.md) | `\n`、`\t`、原始字符串等基础概念 |
| 2 | 函数 | [函数参数传递、`*args` 与 `**kwargs`](python-function-arguments.md) | 可变对象、不可变对象、参数打包与解包 |
| 3 | 迭代 | [生成式、生成器与迭代器](python-comprehensions-generators.md) | 列表生成式、生成器表达式、`yield` |
| 4 | 模块 | [模块导入与 `if __name__ == "__main__"`](python-import-main.md) | 避免导入模块时自动执行脚本代码 |
| 5 | 路径 | [Python 导入路径小结](python-import-path.md) | 绝对导入、相对导入、直接执行脚本的差异 |
| 6 | 命名 | [下划线命名约定](python-underscore-naming.md) | `_var`、`var_`、`__var`、`__dunder__` 的含义 |
| 7 | 正则 | [正则表达式参考](python-regex.md) | 正则表达式入门资料入口 |

## 内容维护建议

- 新增基础主题时，优先放在本目录，并在上表中补充入口。
- 如果某篇笔记变得过长，可以拆成多个更聚焦的小文件。
- 示例代码尽量保持可直接复制运行，并把输出放在独立的 `text` 代码块中。
