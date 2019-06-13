======================
创建Sphinx项目
======================

确认Sphinx安装完成后，打开命令提示符并利用cd命令进入自己想要创建文档的目录，输入sphinx-quickstart并回车，即可打开项目创建向导。

::

    $ sphinx-quickstart 
    Welcome to the Sphinx 1.0.5 quickstart utility.
    
    Please enter values for the following settings (just press Enter to
    accept a default value, if one is given in brackets).
    [...]

sphinx-quickstart详细说明
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
根据向导一步一步设置文档项目，必填项只有项目名称，作者和版本，其他设置都可以一路回车。

1. 文档根目录(Root path for the documentation)，默认为当前目录(.)
#. 是否分离文档源代码与生成后的文档(Separate source and build directories): y
#. 模板与静态文件存放目录前缀(Name prefix for templates and static dir):_
#. 项目名称(Project name) : EvaEngine
#. 作者名称(Author name)：AlloVince
#. 项目版本(Project version) : 1.0.1
#. 文档默认扩展名(Source file suffix) : .rst
#. 默认首页文件名(Name of your master document):index
#. 是否添加epub目录(Do you want to use the epub builder):n
#. 启用autodoc/doctest/intersphinx/todo/coverage/pngmath/ifconfig/viewcode：n
#. 生成Makefile (Create Makefile)：y
#. 生成windows用命令行(Create Windows command file):y

最后会生成Sphinx一个文档项目必需的核心文件，包括：

::

    project
    │ make.bat
    │ Makefile
    ├─build
    └─source
    　　│ conf.py
    　　│ index.rst
    　　├─_static
    　　└─_templates

以下为各个文件的详细说明。

* Makefile：编译过代码的开发人员应该非常熟悉这个文件，如果不熟悉，那么可以将它看作是一个包含指令的文件，在使用 make 命令时，可以使用这些指令来构建文档输出。
* _build：这是触发特定输出后用来存放所生成的文件的目录。
* _static：所有不属于源代码（如图像）一部分的文件均存放于此处，稍后会在构建目录中将它们链接在一起。
* conf.py：这是一个 Python 文件，用于存放 Sphinx 的配置值，包括在终端执行 sphinx-quickstart 时选中的那些值。
* index.rst：文档项目的 root 目录。如果将文档划分为其他文件，该目录会连接这些文件。

生成demo页面
~~~~~~~~~~~~~~
回到project的主目录中，打开命令提示符并运行make html。

::

    $ make html
    sphinx-build -b html -d _build/doctrees   . _build/html
    Making output directory...
    Running Sphinx v1.0.5
    loading pickled environment... not yet created
    building [html]: targets for 2 source files that are out of date
    updating environment: 2 added, 0 changed, 0 removed
    reading sources... [100%] index
    looking for now-outdated files... none found
    pickling environment... done
    checking consistency... done
    preparing documents... done
    writing output... [100%] index 
    writing additional files... genindex search
    copying static files... done
    dumping search index... done
    dumping object inventory... done
    build succeeded.
    
    Build finished. The HTML pages are in _build/html.

生成完毕后，打开build/html/index.html，即可体验由Sphinx生成的静态页面。将下来，我们还将详细讲解reStructuredText的语法以及如何将
我们自己创作的rst文件添加到文档主内容中。

本章小结
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

学习完本章之后，应当能够

* 使用 ``sphinx-quickstart`` 在本地创建Sphinx项目
* 利用 ``make`` 命令生成demo页面