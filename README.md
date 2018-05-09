# Daux.io


[![Latest Version](https://img.shields.io/github/release/dauxio/daux.io.svg?style=flat-square)](https://github.com/dauxio/daux.io/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/dauxio/daux.io/blob/master/LICENSE.md)
[![Build Status](https://img.shields.io/travis/dauxio/daux.io/master.svg?style=flat-square)](https://travis-ci.org/dauxio/daux.io)
[![Coverage Status](https://img.shields.io/scrutinizer/coverage/g/dauxio/daux.io.svg?style=flat-square)](https://scrutinizer-ci.com/g/dauxio/daux.io/code-structure)
[![Quality Score](https://img.shields.io/scrutinizer/g/dauxio/daux.io.svg?style=flat-square)](https://scrutinizer-ci.com/g/dauxio/daux.io)
[![Total Downloads](https://img.shields.io/packagist/dt/daux/daux.io.svg?style=flat-square)](https://packagist.org/packages/daux/daux.io)


**Daux.io** 是一个文档生成器，它使用简单的文件夹结构和Markdown文件即时创建自定义文档。 它可以帮助您以开发人员友好的方式创建精美的文档。

## 功能列表

* 100％移动响应
* 兼容CommonMark ( Markdown 标准)
* 支持Markdown表格
* 自动生成首页/Landing页面
* 自动语法高亮
* 导航自动生成/页面排序
* 4个内置主题或自定义
* 功能性，平面设计风格
* 可共享/可链接的搜索引擎友好网址
* 建立在Bootstrap上
* 无需编译步骤
* Git / SVN友好
* 支持Google Analytics和Piwik Analytics
* 可选代码浮动布局
* 静态网站生成支持

## 演示站点

这是使用Daux.io的网站列表:

- 使用定制主题:
    * [Pixolution flow](https://docs.pixolution.org)
	* [Crafty](https://swissquote.github.io/crafty)
    * [Vulkan Tutorial](https://vulkan-tutorial.com)
    * [TrackJs](http://docs.trackjs.com)
- 使用默认主题
    * [Daux.io](https://daux.io/)
    * [Gltn - An open-source word processor webapp](http://felkerdigitalmedia.com/gltn/docs/)
    * [Invade & Annex 3 - An Arma 3 Co-operative Mission](http://ia3.ahoyworld.co.uk/)
    * [Munee: Standalone PHP 5.3 Asset Optimisation & Manipulation](http://mun.ee)
    * [ICADMIN: An admin panel powered by CodeIgniter.](http://istocode.com/shared/ic-admin/)
    * [Cumulus TV: Android TV app that turns any stream/page into a Live Channel](http://cumulustv.herokuapp.com)
    * [Nuntius: A PHP framework for bots](https://roysegall.github.io/nuntius-bot/)

你使用Daux.io吗？ 向我们发送拉取请求或打开[问题](https://github.com/dauxio/daux.io/issues)，我会将您添加到列表中。

## 安装

### PHP 和 Composer

如果您安装了PHP和Composer，则可以安装依赖项

```bash
composer global require daux/daux.io

# Next to your `docs` folder, run
daux generate
```

然后您可以使用`daux`命令行生成文档。

如果找不到命令，请确保您的`$PATH`包含`〜/.composer/vendor/bin`

### Docker
或者如果你想使用Docker，命令的开始将是：

```bash
docker run --rm -it -w /build -v "$PWD":/build daux/daux.io daux
```

在PHP版本中有效的任何参数在Docker版本中均有效

## 在服务器上运行
   
下载这个版本库作为一个zip文件，解压并将你的文档放在`docs`文件夹中，然后你可以使用Apache或Nginx。

## `daux`
   
命令行工具有两个命令：`generate`和`serve`，不带参数运行Daux.io会自动运行`generate`命令。

你可以运行`daux --help`来获得每个命令的更多细节。

## 文件夹

默认情况下，生成器将在`docs`文件夹中查找文件夹。 将文件夹添加到`docs`文件夹中。 该项目包含一些示例文件夹和文件，以帮助您入门。

您可以将文件夹嵌套到任意数量的级别以获得所需的确切结构。 文件夹结构将被转换为嵌套导航。

如果您希望将文档保存在其他位置（如daux.io根目录之外），则可以在`global.json`文件中指定文档路径。

## 文件
   
生成器将在`docs`文件夹和`docs`内的任何子文件夹内寻找Markdown文件（`* .md`和`* .markdown`）。

您必须使用下划线而不是空格。 以下是一些示例文件名称以及它们将被转换为的内容：

**良好的示例:**

* 01_Getting_Started.md = Getting Started
* API_Calls.md = API Calls
* 200_Something_Else-Cool.md = Something Else-Cool
* _5_Ways_to_Be_Happy.md = 5 Ways To Be Happy

**错误的示例:**

* File Name With Space.md = FAIL

## 排序
   
要以特定方式对文件和文件夹进行排序，您可以用数字和下划线作为前缀，例如， `/docs/01_Hello_World.md` 和 `/docs/05_Features.md` 这将在 *Features* 之前列出 *Hello World*，覆盖默认的字母数字排序。 这些数字将被剥离出导航和网址。 对于文件 `6 Ways to Rich` ，你可以使用 `/docs/_6_Ways_to_Get_Rich.md`

## 登陆页面
   
如果你想为你的项目创建一个漂亮的目标页面，只需在`/docs`文件夹的根目录下创建一个`index.md`文件。 这个文件将被用来创建一个登陆页面。 您还可以使用像这样的配置文件将标语和图像添加到此页面：

```json
{
	"title": "Daux.io",
	"tagline": "The Easiest Way To Document Your Project",
	"image": "app.png"
}
```

注意：图像可以是本地或远程图像。 使用约定`<base_url>`来引用Daux实例的根目录。

## 着陆页Section
   
如果您有兴趣为文档的某个子部分设置着陆页，则只需将“index.md”文件添加到该文件夹即可。 例如，`/docs/01_Examples`因为存在`/docs/01_Examples/index.md`文件而具有该部分的着陆页。 如果您希望为没有着陆页格式的部分设置索引页，请使用名称_index.md

## 配置文件

要定制文档的外观，您可以在`/ docs`文件夹中创建一个`config.json`文件。
`config.json`文件是一个简单的JSON对象，您可以使用它来更改文档的一些基本设置。

### 标题

更改文档中的标题栏

```json
{
	"title": "Daux.io"
}
```

### 主题

我们有4个内置的Bootstrap主题。 要使用其中一个主题，只需将`theme`选项设置为以下之一：

* daux-blue
* daux-green
* daux-navy
* daux-red

```json
{
  "html": { "theme": "daux-green" }
}
```

### 更多选项

许多其他选项可用:

- [全局选项](http://daux.io/Configuration/index)
- [HTML选项](http://daux.io/Configuration/Html_export)
- [Confluence 选项](http://daux.io/Configuration/Confluence_upload)

## 远程运行

将文件从repo复制到可运行PHP 5.4或更高版本的Web服务器。

## 本地运行

有几种方法可以在本地运行文档。
推荐的方法是运行`daux serve`，它将执行PHP的嵌入式服务器。

默认情况下，服务器将运行于：<a href="http://localhost:8085" target="_blank">http//localhost8085</a>

这实际上仅用于在编写/更新大量文档并希望在本地预览更改时使用。

## 生成一组静态文件
   
这些可以上传到静态网站托管服务，如pages.github.com

使用导航生成一整套页面

```bash
daux --source=docs --destination=static
```

## 在IIS上运行
   
如果你已经建立了一个本地或远程的IIS网站，你可能需要一个`web.config`来：

* 重写配置，用于处理干净的URL。
* 如果使用自定义主题，则使用较少文件的MIME类型处理程序。

### 简洁的 URL

`web.config`需要`<system.webServer>`下的<rewrite>条目：

```xml
<configuration>
	<system.webServer>
		<rewrite>
			<rules>
				<rule name="Main Rule" stopProcessing="true">
					<match url=".*" />
					<conditions logicalGrouping="MatchAll">
						<add input="{REQUEST_FILENAME}" matchType="IsFile" negate="true" />
						<add input="{REQUEST_FILENAME}" matchType="IsDirectory" negate="true" />
					</conditions>
					<action type="Rewrite" url="index.php" appendQueryString="false" />
				</rule>
			</rules>
		</rewrite>
	</system.webServer>
</configuration>
```

要在IIS 6上使用干净的URL，您需要使用自定义URL重写模块，例如[URL Rewriter]（http://urlrewriter.net/）。

## Docker

Docker配置还提供在容器中运行daux，您可以使用php5或php7运行daux。

```
cd docker
docker-compose -f docker-compose.7.yml up -d
```

然后，您可以将浏览器指向 http//localhost:8086

## PHP要求
   
Daux.io与PHP 5.6及更高版本兼容。

原因是因为我们有一些依赖（主要是Symfony和Guzzle）不再支持php 5.4。

### 扩展
    
PHP需要以下扩展名：`php-mbstring`和`php-xml`。

如果您遇到类似`utf8_decode（）not found`的错误，这意味着您错过了`php-xml`软件包。(我们已经看到它只发生在PHP 7上）

## 支持
   
如果您需要使用Daux.io的帮助，或发现了错误，请在<a href="https://github.com/dauxio/daux.io/issues" target="_blank"> GitHub repo上创建问题</a>。