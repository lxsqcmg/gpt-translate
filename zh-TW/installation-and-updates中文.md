---
title: "安装和更新Postman"
updated: 2023-05-15
contextual_links:
  - type: section
    name: "先决条件"
  - type: link
    name: "下载和安装"
    url: "https://www.postman.com/downloads/"
  - type: section
    name: "其他资源"
  - type: subtitle
    name: "视频"
  - type: link
    name: "Postman v10新功能介绍 | Postman Intergalactic"
    url:  "https://youtu.be/LmEl7rHYhxU"
  - type: link
    name: "Postman Web客户端代理 | Postman Level Up"
    url:  "https://www.youtube.com/watch?v=6xlJUx2ZMy4&list=PLM-7VG-sgbtC5tNXxd28cmePSa9BYwqeU&index=3"
  - type: subtitle
    name: "博客文章"
  - type: link
    name: "Postman v10发布：API优先世界的API平台"
    url: "https://blog.postman.com/announcing-postman-v10/"
  - type: link
    name: "介绍Postman代理：在浏览器中发送API请求，没有限制"
    url: "https://blog.postman.com/introducing-the-postman-agent-send-api-requests-from-your-browser-without-limits/"
  - type: section
    name: "下一步"
  - type: link
    name: "发送第一个请求"
    url: "/docs/getting-started/sending-the-first-request/"

---

Postman可在Web上使用，网址为**[go.postman.co/home](https://go.postman.co/home)**，也可作为Mac（Intel或Apple Silicon）、Windows（Intel 32位或64位）和Linux（64位）操作系统的本机桌面应用程序使用。

要获取Postman桌面应用程序的最新版本，请访问[下载页面](https://www.postman.com/downloads/)并选择适用于您平台的**下载**。

要获取Postman桌面应用程序的早期版本，请参阅[安装早期版本的Postman](/docs/administration/updating/#installing-earlier-versions-of-postman)。

## 目录

* 在桌面上安装Postman
    * [Windows](#installing-postman-on-windows)
    * [Mac](#installing-postman-on-mac)
    * [Linux](#installing-postman-on-linux)
* [使用Postman Web应用程序](#using-the-postman-web-app)
    * [浏览器要求](#browser-requirements)
    * [安装Postman桌面代理](#installing-the-postman-desktop-agent)
    * [Web限制](#web-limitations)
* [更新Postman](#updating-postman)
* [Chrome应用程序（已弃用）](#postman-chrome-app-deprecated)
    * [迁移到本机应用程序](#migrating-to-the-native-app)
* [在防火墙后使用Postman](#using-postman-behind-a-firewall)
* [解决Postman安装问题](#troubleshooting-your-postman-installation)

## 在Windows上安装Postman

Postman适用于Windows 7及更高版本。

1. [下载](https://www.postman.com/downloads/)最新版本的Postman。
1. 选择并运行`.exe`文件以安装Postman。

> Postman v9.4是支持32位和64位Windows的最后一个版本。在v9.4之后的所有版本的Postman仅适用于64位x86 Windows。您可以继续在32位Windows上使用Postman v9.4及更早版本。

## 在Mac上安装Postman

Postman适用于macOS 10.11（El Capitan）及更高版本。

1. [下载](https://www.postman.com/downloads/)最新版本的Postman。

    > 如果您的Mac配有Apple Silicon处理器，请确保下载**Mac Apple Chip**版本。

1. 如果您的浏览器将文件下载为zip文件，请在**下载**文件夹中找到该文件并解压缩它。
1. 在**下载**文件夹中，双击`Postman`文件以安装它。
1. 在提示时，将文件移动到__Applications__文件夹。这将确保可以正确安装未来的更新。

> 如果您使用第三方压缩应用程序解压缩并安装Postman，则可能会遇到“未加载库”错误。请使用Mac的默认归档实用程序解压缩文件。

您也可以使用[Homebrew](https://brew.sh/)软件包管理器安装Postman：

```sh
brew install --cask postman
```

## 在Linux上安装Postman

您可以通过手动下载、使用[Snap](https://snapcraft.io/postman)存储链接或使用命令`snap install postman`在Linux上安装Postman。

要手动安装，请[下载](https://www.postman.com/downloads/)并解压缩应用程序，例如解压缩到`Downloads`目录中。

要从启动器图标启动应用程序，请创建一个桌面文件。将文件命名为`Postman.desktop`并将其保存在以下位置：

```shell
~/.local/share/applications/Postman.desktop
```

在文件中输入以下内容，将`/path/to/Downloads`替换为文件的位置，并保存：

```shell
[Desktop Entry]
Encoding=UTF-8
Name=Postman
Exec=/path/to/Downloads/Postman/app/Postman %U
Icon=/path/to/Downloads/Postman/app/resources/app/assets/icon.png
Terminal=false
Type=Application
Categories=Development;
```

> Postman支持以下Linux发行版：
>
> * Ubuntu 14.04及更高版本
> * Fedora 24
> * Debian 8及更高版本
>
> 某些Linux发行版的支持取决于它们是否受Electron支持。请参阅[Electron的文档](https://www.electronjs.org/docs/latest/development/build-instructions-linux)。
>
> 建议您安装[Snap](https://snapcraft.io/postman)，因为它包含应用程序所需的所有库，并且这些库与应用程序捆绑在一起。
>
> 避免使用`sudo`命令启动Postman，因为它会在Postman创建的文件上创建权限问题。
>
> 确保您对Postman存储信息的`~/.config`文件夹具有读/写权限。
>
> 如果您是Ubuntu 18用户，则还需要使用命令`apt-get install libgconf-2-4`安装`libgconf-2-4`软件包。

## 使用Postman Web应用程序

您可以在Web浏览器中使用Postman及Postman代理执行API开发和测试任务。要访问Postman Web应用程序，请访问[go.postman.co/home](https://go.postman.co/home)。

> 如果您使用Postman Web应用程序，则Postman建议使用Postman桌面代理以获得最佳体验。有关更多信息，请参见[关于Postman代理](/docs/getting-started/about-postman-agent/)。

### 浏览器要求

Postman Web应用程序针对以下浏览器进行了优化：

* Chrome（78及更高版本）
* Firefox（76及更高版本）
* Edge（79及更高版本）
* Safari（13.1.1及更高版本）

### 安装Postman桌面代理

如果您正在使用Postman Web应用程序，Postman建议下载并安装[Postman桌面代理](/docs/getting-started/about-postman-agent/#the-postman-desktop-agent)，这是一个在您的桌面本地运行的微型应用程序。桌面代理克服了浏览器的跨源资源共享（CORS）限制，并充当从Postman Web应用程序发出API请求的代理。

### Web限制

Postman Web应用程序正在积极开发中。有些功能只能在Postman桌面应用程序中访问，而无法在浏览器中访问：

* **查找和替换** - Postman桌面应用程序支持[在工作区中查找和替换值](/docs/getting-started/navigating-postman/#find-and-replace)，但此功能尚不可在Postman Web应用程序中使用。
* **证书和代理** - Postman桌面应用程序使您能够自定义[证书](/docs/sending-requests/certificates/)和[代理配置](/docs/getting-started/proxy/#configuring-proxy-settings)。在Postman Web应用程序中，这些采用浏览器定义的值，并且无法被Postman覆盖。
* **Postman拦截器** - [拦截器](/docs/sending-requests/capturing-request-data/interceptor/)将浏览器中的cookie同步到Postman桌面应用程序，并直接从浏览器捕获网络请求。无法在Postman Web应用程序中使用拦截器。
* **轻量级Postman API客户端** - 您可以使用[轻量级API客户端](/docs/getting-started/using-api-client/)在未登录Postman的情况下从Postman桌面应用程序发送请求。

## 更新Postman

当有重大更新可用时，Postman桌面应用程序会通知您。对于其他更新，设置图标<img alt="Settings icon" src="https://assets.postman.com/postman-docs/icon-settings-v9.jpg#icon" width="16px">上会有一个点。如果指示器为红色而不是橙色，则表示更新失败。

<img alt="Update Ready" src="https://assets.postman.com/postman-docs/v10/update-ready-v10.jpg" width="300px"/>

选择更新选项以下载或安装最新更新。如果您使用的是Postman v9.13或更高版本，则Postman会自动下载更新。下载完成后，Postman会通知您并提示您重新启动Postman以应用更新。

<img alt="Check for updates" src="https://assets.postman.com/postman-docs/v10/settings-update-v10.jpg"/>

## Postman Chrome应用程序（已弃用）

Postman Chrome应用程序已弃用。如果您使用Chrome应用程序，则可以通过与Postman帐户同步或从Chrome导出并导入到Postman来[切换到使用Postman](#migrating-to-the-native-app)时保留数据。

Postman桌面应用程序基于[Electron](https://www.electronjs.org/)构建，并[克服了Chrome平台的许多限制](https://blog.postman.com/going-native/)。

* 本机应用程序允许您直接使用[cookie](/docs/sending-requests/cookies/)。
* 与Chrome应用程序不同，[拦截器](/docs/sending-requests/capturing-request-data/interceptor/)不需要单独的扩展。
* 本机应用程序配备了内置代理，您可以使用它来[捕获网络流量](/docs/sending-requests/capturing-request-data/capturing-http-requests/)。
* 本机应用程序不受Chrome菜单栏的限制。您可以检查更新、创建Postman Windows和选项卡以及编辑首选项。
* 本机应用程序允许您发送像`Origin`和`User-Agent`这样的标头。这些在Chrome应用程序中受到限制。
* 本机应用程序具有内置的“不要跟随重定向”选项，以防止自动重定向返回300系列响应的请求 - 在Chrome应用程序中执行此操作需要拦截器扩展。
* 本机应用程序具有内置的[控制台](/docs/sending-requests/troubleshooting-api-requests/)，可让您查看API调用的网络请求详细信息。

### 迁移到本机应用程序

要从Chrome应用程序切换到本机应用程序，请[下载](https://www.postman.com/downloads/)Postman并[登录您的帐户](https://go.postman.co/)。启动本机应用程序，您的历史记录和集合将自动同步。

或者，如果您不想登录到Postman帐户，可以从Chrome应用程序中批量导出Postman数据，然后在**设置>数据**中批量导入到新的本机应用程序中。

![Import Export Data](https://assets.postman.com/postman-docs/export-data-v86.jpg)

> 请注意，导入将覆盖您现有的数据。有关批量导入的更多信息，请参见[导入Postman数据](/docs/getting-started/importing-and-exporting-data/)。

## 在防火墙后使用Postman

Postman的基础设施运行在Amazon的AWS平台上。如果您在网络防火墙后操作，则需要允许以下域进行Postman的WebSocket连接：

* `\*.getpostman.com`
* `\*.postman.co`
* `\*.pstmn.io`
* `\*postman.com`

默认情况下，WebSocket连接使用与HTTP（80）和HTTPS（443）相同的端口。对于Postman v10，请允许以下域：

Postman Web应用程序 - WebSocket连接：

* `https://bifrost-web-v10.gw.postman.com`
* `https://bifrost-web-public-v10.gw.postman.com`
* `https://bifrost-web-v10.gw.postman.co`

Postman桌面应用程序 - WebSocket连接：

* `https://bifrost-v10-global.gw.postman.com`
* `https://bifrost-premium-v10-global.gw.postman.com`

Postman桌面应用程序 - HTTP连接：

* `https://bifrost-https-v10.gw.postman.com`
* `https://bifrost-premium-https-v10.gw.postman.com`

Postman没有固定的IP范围可提供。如果需要，请参考[当前的AWS IP范围](https://docs.aws.amazon.com/general/latest/gr/aws-ip-ranges.html)，并允许提供的广泛范围。

## 解决Postman安装问题

如果您遇到任何安装和运行Postman的问题，请查看以下提示。如果这些提示无法帮助您，请参考[社区论坛](https://community.postman.com/tags/installation)上的安装帖子，并在您的问题未被覆盖时创建新帖子。您也可以联系[Postman支持](https://www.postman.com/support)。

### 更新失败错误

如果在Postman中收到__更新失败__通知，则可以使用DevTools进行调查。

![update-error-dialog](https://assets.postman.com/postman-docs/v10/update-error-dialog.jpg)

使用**View > Developer > Show DevTools (Current View)**打开DevTools。

一些已知的错误如下：

* **错误消息** - `Cannot update while running on a read-only volume`
    * 此错误意味着应用程序用户在安装Postman的目录中没有写入权限。要解决问题，请将Postman移动到用户具有写入权限的目录中，例如Mac的`/Application`目录和Linux的`home`目录。

* **错误消息** - `Code signature at URL file:///... did not pass validation: code object is not signed at all`
    * 此错误意味着同时运行多个更新。当应用程序在早期更新完成之前打开时，就会发生这种情况。要解决问题，请退出并重新打开应用程序。

* **错误信息** - `EACCES: permission denied, open '/opt/Postman/Postman-1620288011421.tar.gz`
    * 这个错误意味着应用程序用户在安装Postman的目录中没有写入权限。要解决这个问题，将Postman移动到用户具有写入权限的目录中，例如Linux的`home`目录。

### 无法更新

如果您正在使用Linux的Postman，并且使用Ubuntu软件中心或Snap Store安装了应用程序，则可能没有__检查更新__选项。这是因为更新由商店处理，商店会定期自动更新Postman。