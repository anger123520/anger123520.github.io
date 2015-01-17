#创建说明

这是[Earl Lee](https://anger123520.github.io/)的Git Pages示例!

[代码树](https://github.com/anger123520/anger123520.github.io)欢迎使用,并指正!


## 操作示例

1. 环境环境
1.1 安装Git

请参考[Windows下Git安装指南][1]

1.2 安装node.js

下载：http://nodejs.org/download/

可以下载 node-v0.10.33-x64.msi

安装时直接保持默认配置即可。

2. 配置Github
1.1 建立Repository

建立与你用户名对应的仓库，仓库名必须为【your_user_name.github.io】

1.2 配置SSH-Key

参考[Windows下Git安装指南][1]

3. 安装Hexo
关于Hexo的安装配置过程，请以官方[Hexo][2]给出的步骤为准。

3.1 Installation

打开Git命令行，执行如下命令
``` bash
$ npm install -g hexo
```
3.2 Quick Start

 1. Setup your blog

在电脑中建立一个名字叫「Hexo」的文件夹（比如我建在了D:\Hexo），然后在此文件夹中右键打开Git Bash。执行下面的命令
``` bash
$ hexo init
```
> [info] Copying data
> [info] You are almost done! Don't forget to run `npm install` before you start blogging with Hexo!

Hexo随后会自动在目标文件夹建立网站所需要的文件。然后按照提示，运行 npm install（在 /D/Hexo下）
``` bash
$ npm install
```
会在D:\Hexo目录中安装 node_modules。

 2. Start the server

运行下面的命令（在 /D/Hexo下）
``` bash
$ hexo server
```
> [info] Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.

表明Hexo Server已经启动了，在浏览器中打开 http://localhost:4000/，这时可以看到Hexo已为你生成了一篇blog。

你可以按Ctrl+C 停止Server。

3. Create a new post

新打开一个git bash命令行窗口，cd到/D/Hexo下，执行下面的命令
``` bash
$ hexo new "My New Post"
```
> [info] File created at d:\Hexo\source\_posts\My-New-Post.md

刷新http://localhost:4000/，可以发现已生成了一篇新文章 "My New Post"。

NOTE：
windows下,
有一个问题，发现 "My New Post" 被发了2遍，在Hexo server所在的git bash窗口也能看到create了2次。
``` bash
$ hexo server
```
> [info] Hexo is running at http://localhost:4000/. Press Ctrl+C to stop.
> [create] d:\Hexo\source\_posts\My-New-Post.md
> [create] d:\Hexo\source\_posts\My-New-Post.md
经验证，在hexo new "My New Post" 时，如果按Ctrl+C将hexo server停掉，就不会出现发2次的问题了。

所以，在hexo new文章时，需要stop server。Linux下无该问题

4. Generate static files

执行下面的命令，将markdown文件生成静态网页。
``` bash
$ hexo generate
```
该命令执行完后，会在 D:\Hexo\public\ 目录下生成一系列html，css等文件。

5. 编辑文章

hexo new "My New Post"会在D:\Hexo\source\_posts目录下生成一个markdown文件：My-New-Post.md

可以使用一个支持markdown语法的编辑器（比如 Sublime Text 2）来编辑该文件。

6. 部署到Github

部署到Github前需要配置_config.yml文件，首先找到下面的内容
``` yml
# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type:
然后将它们修改为

# Deployment
## Docs: http://hexo.io/docs/deployment.html
deploy:
  type: github
  repository: https://github.com/anger123520/anger123520.github.io.git
  branch: master
```
NOTE：

如果你是为一个项目制作网站，那么需要把branch设置为gh-pages。

7. 测试

当部署完成后，在浏览器中打开[http://anger123520.github.io/](http://anger123520.github.io/)，正常显示网页，表明部署成功。

8. 总结：部署步骤

每次部署的步骤，可按以下三步来进行。

hexo clean
hexo generate
hexo deploy
9. 总结：本地调试

1. 在执行下面的命令后，

$ hexo g #生成
$ hexo s #启动本地服务，进行文章预览调试
浏览器输入http://localhost:4000，查看搭建效果。此后的每次变更_config.yml 文件或者新建文件都可以先用此命令调试，尤其是当你想调试新添加的主题时。

2. 可以用简化的一条命令

hexo s -g
3.3 命令总结

3.3.1 常用命令

复制代码
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #将.deploy目录部署到GitHub
hexo help  # 查看帮助
hexo version  #查看Hexo的版本
复制代码
3.3.2 复合命令

hexo deploy -g  #生成加部署
hexo server -g  #生成加预览
命令的简写为：

hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
4 配置Hexo
4.1 配置文件介绍

下面的各个部分的介绍，请直接参考[][3]。

1. 默认目录结构介绍

2. _config.yml配置文件介绍

在冒号:后面要留空格

author: Earl Lee
email: 
language: zh-CN
3. 各个主题下的目录介绍（hexo\themes\下的modernist主题为例）

4.2 安装主题

Hexo提供了很多主题，具体可参见[Hexo All Themes][4]。这里我选择使用Pacman主题。具体设置方法如下[Pacman主题介绍][5]

4.2.1 安装

1. 将Git Shell 切到/D/Hexo目录下，然后执行下面的命令，将pacman下载到 themes/pacman 目录下。

$ git clone https://github.com/A-limon/pacman.git themes/pacman
2. 修改你的博客根目录/D/Hexo下的config.yml配置文件中的theme属性，将其设置为pacman。

3. 更新pacman主题
``` bash
cd themes/pacman
git pull
```
NOTE：先备份_config.yml 文件后再升级

4.2.2 配置

如果pacman的默认设置不能满足需要的话，你可以修改 /themes/pacman/下的配置文件_config.yml来定制。

各个config的含义，请参考[Pacman主题介绍][5]中的介绍。

4.3 Custom 404页面

1. 网上大多数教程都将其说的极其简单：“直接在根目录下创建自己的 404.html 就可以”。但我却在这儿废了不少时间，究其原因是大家觉得太简单而说的不够明白。“根目录下”指的不是Hexo目录下，而是Hexo/source目录下。

2. 404.html的内容可以设置为下面的内容[hexo添加404页面][6]（NOTE： _config.yml中的permalink_defaults属性不需要修改）。
``` html
---
layout: default
---
<html>
    <head>
         <meta charset="UTF-8" />
         <title>404</title>                                                                                                                                        
    </head>
    <body>
         <script type="text/javascript" src="http://www.qq.com/404/search_children.js" charset="utf-8"></script>
    </body>
</html>
```
也可以简化为这一行：
``` html
<script type="text/javascript" src="http://www.qq.com/404/search_children.js" charset="utf-8"></script>
```
4.4 安装插件

4.4.1 sitemap插件

1. 可以将你站点地图提交给搜索引擎，文件路径\sitemap.xml。

2. 安装
``` bash
$ npm install hexo-generator-sitemap
```
3. 启用，修改Hexo\_config.yml，增加以下内容

``` yml
# Extensions
Plugins:
- hexo-generator-sitemap

#sitemap
sitemap:
  path: sitemap.xml
```
4. 使用方法

（1）访问 http://localhost:4000/sitemap.xml，即可看到站点地图。

（2）那么怎么将它显示在页面中呢[如何搭建一个独立博客——简明Github Pages与Hexo教程][7]？

可以修改themes/pacman（也就是你正在使用的那个theme）下的 _config.yml，在 menu 节点下添加下面的内容（下面要介绍的RSS插件也同样）
``` yml
menu:
  Home: /
  Archives: /archives
  Rss: /atom.xml
  Sitemap: /sitemap.xml
```

5. 如何向google提交sitemap

Sitemap 可方便管理员通知搜索引擎他们网站上有哪些可供抓取的网页。向google提交自己hexo博客的sitemap，有助于让别人更好地通过google搜索到自己的博客。

如何向google提交sitemap，请参考[如何向google提交sitemap（详细）][8]。

6. 升级插件
``` bash
$ npm update
```
7. 卸载插件
``` bash
$ npm uninstall hexo-generator-sitemap
```
4.4.2 feed插件

1. RSS的生成插件，你可以在配置显示你站点的RSS，文件路径\atom.xml。

2. 安装
``` bash
$ npm install hexo-generator-feed
```
3. 启用，修改Hexo\_config.yml，增加以下内容

``` yml
# Extensions
Plugins:
- hexo-generator-feed
- hexo-generator-sitemap

#Feed Atom
feed:
  type: atom
  path: atom.xml
  limit: 20
```
4.使用方法

参见sitemap插件介绍

5. 优化Hexo
5.1 添加“Fork me on Github” ribbon

给blog主页添加一个“Fork me on Github”的彩带[GitHub Ribbons][9]，比如选择了红色的ribbon，将相应代码复制到Hexo正在使用的theme下layout.ejs中。比如我使用的pacman theme，那么将下面的代码（注意将you改为你自己的github上的注册名）
``` html
<a href="https://github.com/anger123520"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://camo.githubusercontent.com/52760788cde945287fbb584134c4cbc2bc36f904/68747470733a2f2f73332e616d617a6f6e6177732e636f6d2f6769746875622f726962626f6e732f666f726b6d655f72696768745f77686974655f6666666666662e706e67" alt="Fork me on GitHub" data-canonical-src="https://s3.amazonaws.com/github/ribbons/forkme_right_white_ffffff.png"></a>
```
粘贴到 themes\pacman\layout\layout.ejs中，放置在 最后，标签</body>之前即可。
 

6 其他
6.1 中文乱码

在md或yml文件中写中文内容，发布出来后为乱码，原因是文件的编码不对，将文件另存为“UTF-8”编码的文件即可解决问题。

6.2 提交README.md文件到github

每次只执行hexo deploy前,将准备好的README.md拷贝到public目录,再执行hexo deploy.
``` bash
$cp README.md ./pubilc
$hexo deploy
```
References
[1]: http://www.cnblogs.com/zhcncn/p/3787849.html    "Windows下Git安装指南"

[2]: https://github.com/hexojs/hexo     "Hexo"

[3]: http://ibruce.info/2013/11/22/hexo-your-blog/    "hexo你的博客"

[4]: https://github.com/hexojs/hexo/wiki/Themes    "Hexo All Themes"

[5]: http://yangjian.me/pacman/hello/introducing-pacman-theme/   "Pacman主题介绍"

[6]: http://ruocaiwu.github.io/2014/08/14/hexo%E6%B7%BB%E5%8A%A0404%E9%A1%B5%E9%9D%A2/    "hexo添加404页面"

[7]: http://cnfeat.com/2014/05/10/2014-05-11-how-to-build-a-blog/      "如何搭建一个独立博客——简明Github Pages与Hexo教程"

[8]: http://fionat.github.io/blog/2013/10/23/sitemap/    "如何向google提交sitemap（详细）"

[9]: https://github.com/blog/273-github-ribbons    "GitHub Ribbons"

