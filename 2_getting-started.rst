===========
安装Sphinx
===========

Sphinx本身是用Python语言写成，同时支持Python2.7及Python3.3以上的版本。官方推荐使用Python3。以下为各个不同系统的详细安装说明。

Linux系统
~~~~~~~~~~~~~~
以下为各个版本的Linux的安装说明。

Debian/Ubuntu
-----------------------------
在终端中使用 :command:`apt-get`: 命令加上 ``python3-sphinx`` (Python 3) 或者 ``python-sphinx`` (Python 2) 即可进行安装。
例如：

::

   $ apt-get install python3-sphinx

假如系统中没有安装Python，该命令会直接将其安装

RHEL, CentOS
-----------------------------
在终端中使用 :command:`yum`: 命令加上 ``python-sphinx`` 进行安装。
例如：

::

   $ yum install python-sphinx

假如系统中没有安装Python，该命令会直接将其安装

其他Linux发行版
-----------------------------
大部分Linux发行版已经包括了Sphinx类库。类库的名字一般是 ``python3-sphinx`` 、 ``python-sphinx`` 或者 ``sphinx``。
但是请注意有其他两个类库的名字中也包含 ``sphinx`` ，分别是一个叫 *CMU Sphinx* 的语音识别工具和一个数据库全文搜索插件 *Sphinx search* .

MacOS
~~~~~~~~~~~~~~
在MacOS中，可以使用 `Homebrew`__ 、 `MacPorts`__ 或者 `Anaconda`__ 之类的Python发行版安装Sphinx。

__ https://brew.sh/
__ https://www.macports.org/
__ https://www.anaconda.com/download/#macos

Homebrew
-----------------------------
::

   $ brew install sphinx-doc

如果想了解更多信息，可以参考`package overview`__。

__ http://formulae.brew.sh/formula/sphinx-doc

MacPorts
-----------------------------
使用 :command:`port`: 加上 ``python36-sphinx`` (Python 3) or ``python27-sphinx`` (Python 2) 安装Sphinx。

::

   $ sudo port install py36-sphinx

如果需要添加环境变量，请使用 ``port select`` 命令。

::

   $ sudo port select --set python python36
   $ sudo port select --set sphinx py36-sphinx

如果想了解更多信息，可以参考`package overview`__.

__ https://www.macports.org/ports.php?by=library&substr=py36-sphinx

Anaconda
-----------------------------
运行以下命令即可完成安装。

::

   $ conda install sphinx

Windows
~~~~~~~~~~~~~~
一般而言，Windows系统没有预装Python，因此需要自己手动下载安装 `Python 3`__ 或者 `Python 2.7`__ 。推荐安装Python3。
安装完Python后，可以在命令提示符中直接使用 :command:`pip` 命令安装。

使用PyPI进行安装
~~~~~~~~~~~~~~~~~~~

`Python Package Index <https://pypi.org/project/Sphinx/>`_ 上面提供了Sphinx的包，因此可以直接使用 :command:`pip` 命令进行安装。
在Linux或MacOS上，直接打开终端并运行以下命令即可。

::

   $ pip install -U sphinx

在Windows上，在命令提示符中输入同样的命令。

.. code-block:: doscon

   C:\> pip install -U sphinx

安装完成后，在命令提示符中输入 :command:`sphinx-build --version` ，若出现Sphinx版本号，即证明已经安装成功。
如果使用 *PyPI* 安装，默认会安装Sphinx的最新版本。如果最新版本中有Bug而需要安装之前的版本，可以在pip命令中加上 ``--pre`` 参数。

::

   $ pip install -U --pre sphinx

从其他源安装
~~~~~~~~~~~~~~~~~~~
可以直接从Sphinx的 `Git repository`__ 下载并编译。只需要首先使用 :command:`git` 命令将仓库克隆到本地再进行安装即可。

::

   $ git clone https://github.com/sphinx-doc/sphinx
   $ cd sphinx
   $ pip install .

::

   $ pip install git+https://github.com/sphinx-doc/sphinx


也可以从网页上以 `tar.gz`__ 或者 `zip`__ 格式将Sphinx以压缩包的形式保存下来。下载完成为，同样可以使用 :command:`pip` 命令进行安装。

.. highlight:: default

__ https://github.com/sphinx-doc/sphinx
__ https://github.com/sphinx-doc/sphinx/archive/master.tar.gz
__ https://github.com/sphinx-doc/sphinx/archive/master.zip

本章小结
~~~~~~~~~~~~~~

学习完本章后，在命令提示符或者终端中输入

::

    sphinx-quickstart --v

应该能够显示Sphinx版本号