**Daux.io** 是一个文档生成器，它使用简单的文件夹结构和Markdown文件即时创建自定义文档。 它可以帮助您以开发人员友好的方式创建精美的文档。

[TOC]

## 功能列表

### 对文档作者来说

* [导航自动生成/页面排序](01_Features/Navigation_and_Sorting.md)
* [内部文档关联](01_Features/Internal_links.md)
* [兼容CommonMark](01_Features/CommonMark_compliant.md)
* [自动生成首页/Landing页面](01_Features/Landing_page.md)
* [多种输出格式](01_Features/Multiple_Output_Formats.md)
* [多语言支持](01_Features/Multilanguage.md)
* [无需编译步骤](01_Features/Live_mode.md)
* [静态网站生成支持](01_Features/Static_Site_Generation.md)
* [内容目录支持](01_Features/Table_of_contents.md)

### 对开发人员来说

* [自动语法高亮](01_Features/Auto_Syntax_Highlight.md)
* [扩展Daux.io的处理器](01_For_Developers/Creating_a_Processor.md)
* 完全访问内部API以编程方式创建新页面
* 使用页面元数据

### 对市场人员来说

* 100％移动响应
* 4个内置主题或自定义
* 功能性，平面设计风格
* 可选代码浮动布局
* 可共享/可链接的搜索引擎友好网址
* 支持Google Analytics和Piwik Analytics

## 演示站点

这是使用Daux.io的网站列表:

* [Daux.io](https://dauxio.github.io/)
* [DoctrineWatcher](https://dsentker.github.io/WatcherDocumentation/)
* [jDrupal](http://jdrupal.easystreet3.com/8/docs/)
* [DrupalGap](http://docs.drupalgap.org/8/)
* [Invade & Annex 3 - An Arma 3 Co-operative Mission](http://ia3.ahoyworld.co.uk/)
* [Munee: Standalone PHP 5.3 Asset Optimisation & Manipulation](http://mun.ee)
* [ICADMIN: An admin panel powered by CodeIgniter.](http://istocode.com/shared/ic-admin/)

你使用Daux.io吗？ 向我们发送拉取请求或打开[问题](https://github.com/dauxio/daux.io/issues)，我会将您添加到列表中。

## 入门

### 安装

#### PHP 和 Composer

如果您安装了PHP和Composer，则可以安装依赖项

```bash
composer global require daux/daux.io

# Next to your `docs` folder, run
daux generate
```

然后您可以使用`daux`命令行生成文档。

如果找不到命令，请确保您的`$PATH`包含`〜/.composer / vendor / bin`

#### Docker
或者如果你想使用Docker，命令的开始将是：

```bash
docker run --rm -it -w /build -v "$PWD":/build daux/daux.io daux
```

在PHP版本中有效的任何参数在Docker版本中均有效


### 编写页面

创建新页面非常简单：
1.创建一个Markdown文件（`*.md`或`*.markdown`）
2.开始写作

默认情况下，生成器将在`docs`文件夹中查找文件夹。
将文件夹添加到`docs`文件夹中。 该项目包含一些示例文件夹和文件，以帮助您入门。

您可以将文件夹嵌套到任意数量的级别以获得所需的确切结构。
文件夹结构将被转换为嵌套导航。

您必须使用下划线而不是空格。 以下是一些示例文件名称以及它们将被转换为的内容：

**良好的示例:**

* 01_Getting_Started.md = Getting Started
* API_Calls.md = API Calls
* 200_Something_Else-Cool.md = Something Else-Cool
* _5_Ways_to_Be_Happy.md = 5 Ways To Be Happy

**错误的示例:**

* File Name With Space.md = FAIL

### 查看你的网页

现在你可以看到你的页面。 你有两个选择：直接提供服务，或者生成各种格式。

我们在撰写文档时建议您使用第一种，在写作时您会得到更快的反馈。

#### 文件服务

通过在文档的根目录下运行以下命令，可以使用PHP的嵌入式Web服务器

```
./serve
```

将您的文件上传到apache/nginx服务器并查看您的文档

[更多信息在这里](01_Features/Live_mode.md)

#### 导出为其他格式

Daux.io是可扩展的，默认情况下有三种导出格式：

- 导出为HTML，与网站相同，但可以不使用PHP进行托管。
- 在单个HTML页面中导出所有文档
- 上传到您的Atlassian Confluence服务器。

[查看详细的功能比较矩阵](01_Features/Multiple_Output_Formats.md)

要输出，运行`daux`命令，你的文档将以`static`生成（你可以用`--destination`选项改变目的地）

[在这里查看所有选项](01_Features/Static_Site_Generation.md)

## 配置信息

现在你已经掌握了基本知识，你也可以[看看你可以配置什么](05_Configuration/_index.md)

## PHP要求

Daux.io与PHP 5.6及更高版本兼容。

原因是因为我们有一些依赖关系不再支持php 5.5。

### 扩展

PHP需要以下扩展名：`php-mbstring`和`php-xml`。

如果您遇到类似`utf8_decode（）not found`的错误，这意味着您错过了`php-xml`软件包。 （我们已经看到它只发生在PHP 7上）

## 已知的问题

- __Windows UTF-8 files support__ 具有UTF-8字符的文件无法在Windows 系统上使用PHP5中处理，PHP7应该可以正常工作。.


## 支持

如果您需要使用Daux.io的帮助，或发现了错误，请在<a href="https://github.com/dauxio/daux.io/issues" target="_blank"> GitHub repo上创建问题</A>。