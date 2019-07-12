# www.egolee.com
苏州易格勒贸易有限公司

#使用hexo搭建github.io博客
##前言
习惯自己写Blog的朋友一定不会陌生Wordpress，或许也曾在新浪博客和QQ空间留过脚印，但静心认真思考一下，似乎我们又总是向往更加简单自由的写作方式。
GitHub给我们提供了一个无限的空间，我们需要珍惜使用，而Hexo的出现从某种意义上来说代替了Jekyll，
让我们可以更专注于写作本身。本文主要介绍自己的实践心得并不断完善内容，衍生知识和原理推荐大家认真阅读官网的手册，其它推荐参考内容链接在文中也会标注出来。

阮一峰 - 喜欢写Blog的人，会经历三个阶段

第一阶段，刚接触Blog，觉得很新鲜，试着选择一个免费空间来写。 第二阶段，发现免费空间限制太多，就自己购买域名和空间，搭建独立博客。
*第三阶段，觉得独立博客的管理太麻烦，最好在保留控制权的前提下，让别人来管，自己只负责写文章。

更新历史

2015年11月18日 - 推荐iissnan的主题，完善细节内容 2015年09月03日 - 完善Windows 10安装Hexo中的细节
2015年03月22日 - 更新Windows下Hexo 3.0安装和升级，感谢@机智的阿卡林酱 2015年03月10日 - 增加Hexo 3.0降级 2.8
2014年12月19日 - 完善内容 2014年12月09日 - 更新Hexo配置修改部分
2014年06月19日 - 更新全部基础架构，待完善配置修改部分 2014年06月17日 - 更新部分Hexo建站过程，待完善
*2014年05月29日 - 撰写初稿

阅读原文 - [https://wsgzao.github.io/post/hexo-guide/]

扩展阅读

Hexo Docs - [http://hexo.io/docs/]
HelloDog Index - [https://wsgzao.github.io/index/#Hexo]
##准备工作
注意 本文主要针对Windows平台和Hexo 3.x

###了解Hexo
A fast, simple & powerful blog framework

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，
在几秒内，即可利用靓丽的主题生成静态网页。
hexo.io

###安装GIT
GitHub Windows

简单可依赖，安装完成后依据提示操作即可，So Easy

###安装Node.JS
Node.JS

注意 安装完成后添加Path环境变量，使npm命令生效。
新版已经会自动配置Path

;C:\Program Files\nodejs\node_modules\npm
安装Hexo
配置好GitHub家目录后，双击桌面上的Git Shell，输入npm命令即可安装

install hexo-cli -g```
```npm install hexo --save
#如果命令无法运行，可以尝试更换taobao的npm源
npm install -g cnpm –registry=https://registry.npm.taobao.org
Hexo初始化配置
创建Hexo文件夹
安装完成后，根据自己喜好建立目录（如D:\myBlog\hexo），
进入vscode 切换到hexo路径执行以下指令

init```
#安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
$ hexo init 
$ cd 
$ npm install

#新建完成后，指定文件夹的目录如下
.
├── _config.yml
├── package.json
├── scaffolds
├── scripts
├── source
|      ├── _drafts
|      └── _posts
└── themes
安装Hexo插件 
```node
npm install hexo-generator-index --save
npm install hexo-generator-archive --save
npm install hexo-generator-category --save
npm install hexo-generator-tag --save
npm install hexo-server --save
npm install hexo-deployer-git --save
npm install hexo-deployer-heroku --save
npm install hexo-deployer-rsync --save
npm install hexo-deployer-openshift --save
npm install hexo-renderer-marked@0.2 --save
npm install hexo-renderer-stylus@0.2 --save
npm install hexo-generator-feed@1 --save
npm install hexo-generator-sitemap@1 --save
本地查看效果
继续执行以下命令，成功后可登录localhost:4000查看效果

server```
## Quick Start

### Create a new post

``` bash
$ hexo new "My New Post"
More info: Writing

Run server
$ hexo server
More info: Server

Generate static files
$ hexo generate
More info: Generating

Deploy to remote sites
$ hexo deploy
More info: Deployment

Hexo简写命令
hexo n #生成文章，或者source_posts手动编辑
hexo s #本地发布预览效果
hexo g #生成public静态文件
最后我选择手动同步更新至GitHub
部署静态网页到GitHub
注册设置GitHub
登录GitHub，注册自定义用户名如wsgzao
在主页右下角创建New repository，name必须和用户名一致如sunscheung.github.io
首次创建耐心等待10分钟左右审核，之后即可访问静态主页如https://sunscheung.github.io
同步内容至GitHub
下载GitHub Windows
设置Local path如D:\myBlog\
运行Git Shell切换到如D:\myBlog\hexo路径下
执行hexo g命令生成public文件夹
把生成的内容全部拷贝到Local path或其子目录
运行GitHub确认修改信息后执行右上角的Sync同步
最后访问主页观察效果
[https://pages.github.com/]

域名和DNS
域名推荐
GoDaddy makes registering Domain Names fast, simple, and affordable.
【推荐理由】两个字“靠谱”，支持支付宝，附优惠码链接

[http://www.godaddy.com/]
[http://www.gdcodecoupon.com/]

DNS推荐
致力于为您提供最稳定、最安全的域名解析服务
【推荐理由】依然是两个字“靠谱”，感谢他们一直以来对于公益的坚持

[https://www.dnspod.cn/]
设置CNAME
在Github的网站目录下创建CNAME文件
填写自己的域名如hellodog.com，保存结束
登录DNSPod，先添加域名，然后添加记录，设置如下
主机记录 记录类型 线路类型 记录值 MX优先级 TTL
@ CNAME 默认 wsgzao.github.io. - 10
www CNAME 默认 wsgzao.github.io. - 10
Hexo配置修改
告诉自己为什么要选择Hexo

知识储备

[ ]1.勤学勤练Markdown

本地+云端备份数据是一种习惯

Markdown学习路径 - [https://wsgzao.github.io/post/markdown/]

[x]2.使用性感的文本编辑器

工欲善其事必先利其器

Notepad2
Sublime Text
https://wsgzao.github.io/post/windows/#文本编辑器

##Hexo主题
选择主题建议遵循KISS原则

Hexo Themes - [http://hexo.io/themes/]
Jacman - [https://wsgzao.github.io/post/hexo-jacman/]
iissnan - [http://notes.iissnan.com]
##常见问题

###1.修改配置文件时注意YAML语法，参数冒号:后一定要留空格

###2.中文乱码请修改文件编码格式为UTF-8

如何迁移至Hexo
[http://hexo.io/zh-cn/docs/migration.html]
