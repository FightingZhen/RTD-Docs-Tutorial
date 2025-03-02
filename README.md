# RTD-Docs-Tutorial
记录通过Markdown + Sphinx + ReadTheDocs构建个人技术文档全流程

# 环境准备
## Sphinx安装
Sphinx是一个基于python的文档生成工具，支持处理MarkDown格式撰写的文档，可以与Read the Docs平台很好的配合

```shell
# 安装Sphinx及相关的依赖
pip install -U Sphinx

pip install sphinx-autobuild
pip install sphinx_rtd_theme
pip install recommonmark
pip install sphinx_markdown_tables
```

# 项目构建
## 使用Sphinx快速构建文档项目
在命令行输入`sphinx-quickstart`启动创建流程，包含如下步骤：
- `Separate source and build directories (y/n)`：是否将文档资源(source)和构建后的文件(build)独立存放，推荐选`y`
- `Project name`：项目名称
- `Author name(s)`：项目作者
- `Project release`：版本号
- `Project language [en]`：项目语言，如想用中文可配置`zh_CN`

构建完成后，在本地生成的项目文件结构如下：
- source：
    - _static：存放静态文件
    - _templates：存放模板
    - conf.py：Sphinx配置
    - index.rst：文档起始文件
- build：构建生成文件的保存目录
- Makefile：构建相关指令
- make.bat：Windows平台构建启动脚本

## 验证项目
通过命令`sphinx-autobuild source build/html`可在本地快速启动一个服务，通过命令行提供的`http://127.0.0.1:8000`访问预览

## 修改主题
可以修改`conf.py`文件中的`html_theme`字段来修改主题，主流主题包括`sphinx_rtd_theme`

## 支持Markdown类型文件
在`source/conf.py`文件中，添加以下依赖即可：
```python
extensions = [
    'recommonmark',
    'sphinx_markdown_tables'
 ]
```

## index.rst文件格式
index.rst文件作为整个项目的起始文件，起到全局内容编排的作用，主要包括3部分：
1. 首页的标题
2. 首页的正文
3. 目录编排，参考下方实现方式，支持在index.rst中编排多组
    ```text
    .. toctree::
       :maxdepth: 显示标题层级数（如设置为1仅显示一级标题）
       :caption: 分组的子标题
    
       文件1绝对路径（相对于index.rst文件开始的绝对路径）
       文件2绝对路径（相对于index.rst文件开始的绝对路径）
    ```

# 参考项目
基于上述流程，我构建了自己的在线文档[FightingZhen/ascend-pt-ecosystem-docs](https://github.com/FightingZhen/ascend-pt-ecosystem-docs)，欢迎参考并提出您的宝贵意见及建议:)

# 参考文档
- [Sphinx + Read the Docs 从懵逼到入门 - 阿基米东的文章 - 知乎](https://zhuanlan.zhihu.com/p/264647009)
- [WeiChunyu/MS-GameTutorial](https://gitee.com/WeiChunyu-star/MS-GameTutorial)
