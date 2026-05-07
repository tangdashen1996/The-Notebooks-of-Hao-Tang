# The Notebooks of Hao Tang

一个以 Python 基础知识为主的个人学习笔记仓库。这里的内容从零散随记整理为“主题索引 + 分类笔记”的结构，方便后续回顾、补充和扩展。

## 仓库结构

```text
.
├── README.md                 # 仓库入口与阅读指南
└── docs/
    └── python-basics/        # Python 基础主题笔记
        ├── README.md         # Python 基础笔记索引
        ├── python-comprehensions-generators.md
        ├── python-function-arguments.md
        ├── python-import-main.md
        ├── python-import-path.md
        ├── python-regex.md
        ├── python-strings.md
        └── python-underscore-naming.md
```

## 快速阅读

如果你正在系统复习 Python 基础，建议按下面顺序阅读：

1. [字符串与转义](docs/python-basics/python-strings.md)
2. [函数参数传递、`*args` 与 `**kwargs`](docs/python-basics/python-function-arguments.md)
3. [生成式、生成器与迭代器](docs/python-basics/python-comprehensions-generators.md)
4. [模块导入与 `if __name__ == "__main__"`](docs/python-basics/python-import-main.md)
5. [Python 导入路径小结](docs/python-basics/python-import-path.md)
6. [下划线命名约定](docs/python-basics/python-underscore-naming.md)
7. [正则表达式参考](docs/python-basics/python-regex.md)

完整目录见 [Python 基础笔记索引](docs/python-basics/README.md)。

## 整理约定

后续新增笔记时，建议遵守以下约定：

- **按主题归档**：同一主题放在同一个子目录下，例如 `docs/python-basics/`。
- **文件名使用英文 kebab-case**：例如 `python-import-path.md`，方便跨平台和 URL 访问。
- **每篇笔记包含标题、要点和示例**：先给结论，再放代码，最后补充注意事项。
- **外部资料集中放在“延伸阅读”**：正文尽量保持简洁，避免链接打断阅读。

## 当前状态

这是一个持续整理中的个人知识库。内容以“可快速复习”为优先级，不追求一次性覆盖所有细节。
