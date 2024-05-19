# 序言

当我们构建用户界面时，解决的最困难的问题之一是同步开发人员在代码中管理的数据和向用户显示的数据。开发人员采取的第一步是将演示和逻辑分开。这种分离使开发人员能够更好地分别管理两侧。但这两个层之间的通信仍然很困难。那是因为 JavaScript 被认为是一种不重要的语言，我们过去只是用它进行验证。然后 jQuery 给了我们一个线索，说明这种语言有多强大。但是数据仍然在服务器上管理，我们只是显示静态演示。这使得用户体验差和缓慢。

在过去的几年中，一种新型的架构模式出现了。它被称为 MVVM 模式。使用这种模式的库和框架使开发人员能够轻松地同步视图和数据。其中一个库就是 Knockout，使用 Knockout 的框架名为 Durandal。

Knockout 是一个快速且跨浏览器兼容的库，可以帮助我们开发具有更好用户体验的客户端应用程序。

开发人员不再需要担心数据同步的问题。Knockout 将我们的代码绑定到 HTML 元素，实时向用户显示我们代码的状态。

这种动态绑定使我们忘记了编码同步，我们可以将精力集中在编写应用程序的重要功能上。

如今，管理这些框架对前端开发人员来说是必不可少的。在本书中，你将学习 Knockout 和 Durandal 的基础知识，并且我们将深入探讨 JavaScript 的最佳设计实践和模式。

如果你想改进应用程序的用户体验并创建完全操作的前端应用程序，Knockout 和 Durandal 应该是你的选择。

# 本书涵盖内容

第一章，*使用 KnockoutJS 自动刷新 UI*，教你关于 Knockout 库。你将创建可观察对象并使你的模板对变化具有反应性。

第二章，*KnockoutJS 模板*，展示了如何创建模板以减少 HTML 代码。模板将帮助您保持设计的可维护性，并且它们可以根据您的数据进行调整。

第三章，*自定义绑定和组件*，展示了如何扩展 Knockout 库以使您的代码更易维护和可移植。

第四章, *管理 KnockoutJS 事件*，教你如何使用 jQuery 事件与隔离的模块和库进行通信。事件将帮助你在不同组件或模块之间发送消息。

第五章，*从服务器获取数据*，展示了如何使用 jQuery AJAX 调用从客户端与服务器通信。您还将学习如何使用模拟技术在没有服务器的情况下开发客户端。

第六章，*模块模式 – RequireJS*，教您如何使用模块模式和 AMD 模式编写良好形式的模块以管理库之间的依赖关系。

第七章，*Durandal – The KnockoutJS Framework*，教您最好的 Knockout 框架是如何工作的。您将了解框架的每个部分，从而能够用更少的代码制作大型应用程序。

第八章，*Durandal – The Cart Project*，将本书中构建的应用程序迁移到 Durandal。你将用几行代码开发同样的应用程序，并能够添加新功能。

# 本书所需内容

下面是在不同阶段需要的软件应用程序列表：

+   要开始：

    +   Twitter Bootstrap 3.2.0

    +   jQuery 2.2.1

    +   KnockoutJS 3.2.0

+   为了管理高级模板：

    +   Knockout 外部模板引擎 2.0.5

+   用于从浏览器执行 AJAX 调用的服务器：

    +   Mongoose 服务器 5.5

+   为了模拟数据和服务器调用：

    +   Mockjax 1.6.1

    +   MockJSON

+   要验证数据：

    +   Knockout 验证 2.0.0

+   使用浏览器进行调试：

    +   Chrome Knockout 调试器扩展

+   为了管理文件依赖关系：

    +   RequireJS

    +   Require 文本插件

    +   Knockout 和 helpers

+   KnockoutJS 框架：

    +   Durandal 2.1.0 Starter Kit

+   其他：

    +   iCheck 插件 1.0.2

# 本书适合谁

如果您是一名 JavaScript 开发人员，一直在使用 DOM 操作库（如 jQuery、MooTools 或 Scriptaculous），并且希望在现代 JavaScript 开发中进一步使用简单、轻量级和文档完善的库，那么这项技术和本书就适合您。

学习 Knockout 将是构建响应用户交互的 JavaScript 应用程序的下一个完美步骤。

# 约定

在本书中，您会发现许多文本样式，用于区分不同类型的信息。以下是一些这些样式的示例以及它们的含义解释。

文本中的代码字、数据库表名、文件夹名、文件名、文件扩展名、路径名、虚拟 URL、用户输入和 Twitter 句柄如下所示：“例如，`background-color` 会抛出错误，因此您应该写成 `'background-color'`。”

代码块如下所示：

```js
var cart = ko.observableArray([]);
var showCartDetails = function () {
  if (cart().length > 0) {
    $("#cartContainer").removeClass("hidden");
  }
};
[default]
exten => s,1,Dial(Zap/1|30)
exten => s,2,Voicemail(u100)
exten => s,102,Voicemail(b100)
exten => i,1,Voicemail(s0)
```

当我们希望引起您对代码块中特定部分的注意时，相关行或项目将以粗体显示：

```js
[default]
exten => s,1,Dial(Zap/1|30)
exten => s,2,Voicemail(u100)
exten => s,102,Voicemail(b100)
exten => i,1,Voicemail(s0)
<button class="btn btn-primary btn-sm" data-bind="click: showCartDetails, enable: cart().length  > 0">
  Show Cart Details
</button>

<button class="btn btn-primary btn-sm" data-bind="click: showCartDetails, disable: cart().length  < 1">
  Show Cart Details
</button>
```

任何命令行输入或输出如下所示：

```js
# cp /usr/src/asterisk-addons/configs/cdr_mysql.conf.sample
 /etc/asterisk/cdr_mysql.conf

```

**新术语**和**重要词汇**以粗体显示。您在屏幕上看到的单词，例如菜单或对话框中的单词，会以这种方式出现在文本中："一旦我们点击了**确认订单**按钮，订单应该显示给我们以审查，并确认我们是否同意。"

### 注意

警告或重要提示会以这样的框中出现。

### 提示

小贴士和技巧会出现在这样的格式中。

# 读者反馈

我们的读者反馈随时欢迎。请告诉我们您对这本书的看法——您喜欢或不喜欢的内容。读者反馈对我们很重要，因为它帮助我们开发出您真正能充分利用的标题。

要向我们发送一般反馈，只需发送电子邮件至 `<feedback@packtpub.com>`，并在您的邮件主题中提及书名。

如果有您在其中具有专业知识并且有兴趣撰写或为一本书作出贡献的主题，请查看我们的作者指南，网址为[www.packtpub.com/authors](http://www.packtpub.com/authors)。

# 客户支持

现在您是 Packt 书籍的自豪所有者，我们有很多东西可以帮助您充分利用您的购买。

## 下载示例代码

您可以从您在[`www.packtpub.com`](http://www.packtpub.com)的帐户中下载示例代码文件，这适用于您购买的所有 Packt Publishing 书籍。如果您在其他地方购买了此书，您可以访问[`www.packtpub.com/support`](http://www.packtpub.com/support)并注册，以便将文件直接通过电子邮件发送给您。

## 勘误

尽管我们已经尽一切努力确保内容的准确性，但错误确实会发生。如果您在我们的书籍中发现错误——也许是文字或代码中的错误——我们将不胜感激地向您报告。通过这样做，您可以避免其他读者的挫折，并帮助我们改进此书的后续版本。如果您发现任何勘误，请访问[`www.packtpub.com/submit-errata`](http://www.packtpub.com/submit-errata)，选择您的书籍，单击**勘误提交表单**链接，然后输入勘误的详细信息。一旦您的勘误得到验证，您的提交将被接受，并且勘误将被上传到我们的网站或添加到该标题的现有勘误列表的**勘误**部分中。

要查看先前提交的勘误，请转到[`www.packtpub.com/books/content/support`](https://www.packtpub.com/books/content/support)，并在搜索字段中输入书名。所需信息将出现在**勘误**部分下。

## 盗版

在互联网上盗版受版权保护的材料是各种媒体的持续问题。在 Packt，我们非常重视版权和许可证的保护。如果您在互联网上发现我们作品的任何形式的非法副本，请立即向我们提供位置地址或网站名称，以便我们采取措施。

请通过<copyright@packtpub.com>与我们联系，提供疑似盗版材料的链接。

我们感谢您在保护我们的作者和我们为您带来有价值内容的能力方面的帮助。

## 问题

如果您对本书的任何方面有问题，请通过<questions@packtpub.com>与我们联系，我们将尽力解决问题。
