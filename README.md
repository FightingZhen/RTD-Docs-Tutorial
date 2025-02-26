# docs-tutorial
记录通过Sphinx+ReadTheDocs构建个人技术文档全流程。

# 环境准备
## Sphinx安装
Sphinx是一个基于python的文档生成工具，支持处理MarkDown格式撰写的文档，可以与Read the Docs平台很好的配合。

```shell
# 安装Sphinx及相关的依赖
pip install -U Sphinx

pip install sphinx-autobuild
pip install sphinx_rtd_theme
pip install recommonmark
pip install sphinx_markdown_tables
```
## 使用Sphinx快速构建文档项目
在命令行输入`sphinx-quickstart`启动创建流程，包含如下步骤：
- `Separate source and build directories (y/n)`：是否将文档资源(source)和构建后的文件(build)独立存放，推荐选`y`
- `Project name`：项目名称
- `Author name(s)`：项目作者
- `Project release`：版本号
- `Project language [en]`：项目语言，如想用中文可配置`zh_CN`

# 参考文档
[Sphinx + Read the Docs 从懵逼到入门 - 阿基米东的文章 - 知乎](https://zhuanlan.zhihu.com/p/264647009)
