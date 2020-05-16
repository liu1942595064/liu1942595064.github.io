---
title: 【三】nodejs和vue的安装教程
date: 2020-05-16 15:34:36
tags:
  - node.js安装
  - vue安装
categores:
  - node.js
  - vue
description: node.js 和 vue的安装教程
---
> ###### 写给接下来需要学vue的小伙伴


## 前言
本博主也走过很多很多坑，才逐渐有了经验，如果这篇文章对你有帮助
请转发至需要过坑的小伙伴，本文助他飞过去。
-----------------------------------------
<!-- more -->

### 安装nodejs

选择对应版本，https://nodejs.org/en/download/
选好安装路径，最好不要安装在c盘（就是系统盘），占系统盘空间。
（安装时选好路径一直选默认就行，当然不放心你也可以去问度娘（百度）或谷哥（Chrome））

cmd里查看nodejs和vue的安装版本（主要是检查是否安装正确）

安装好之后，对npm安装的全局模块所在路径以及缓存所在路径，进行环境配置。
是因为以后在执行类似：npm install express [-g]（后面的可选参数-g，g代表global全局安装的意思）的安装语句时，会将安装的模块安装到【C:\Users\用户名\AppData\Roaming\npm】路径中，占C盘空间。
例如：我希望将全模块所在路径和缓存路径放在我node.js安装的文件夹中，则在我安装的文件夹【D:\Develop\nodejs】下创建两个文件夹【node_global】及【node_cache】打开cmd输入如下命令
```
npm config set prefix "D:\Develop\nodejs\node_global"
npm config set cache "D:\Develop\nodejs\node_cache"
```


接下来点击 我的电脑，属性，高级系统设置
选择高级，环境变量
1.新建系统变量
```
输入NODE_PATH
输入D:\Develop\nodejs;D:\Develop\nodejs\node_global\node_modules    （node安装地址跟自定义地址 用;分开）
```
2.修改用户变量path
```
%NODE_PATH%;D:\Develop\nodejs\node_global   (加%NODE_PATH%是为了防止 cmd找不到node报错）
```
修改完后保存


------------------------


### 使用nodejs安装vue-cli脚手架

前提：nodeJs本地已安装。
1、执行npm install --global vue-cli ，全局安装vue-cli
----因为默认是从国外服务器下，可以使用阿里巴巴在国内的镜像服务器。
产生通过config命令设置默认下载路径：
```
npm config set registry https://registry.npm.taobao.org
```
然后再执行：
```
npm install --global vue-cli
```

2、安装后，检查是否安装成功
vue -V (在此注意V为大写)
3、使用vue建一个项目名叫“my-project”（vue init webpack my-project），注意项目名不能有大写。
----注：vue-cli 的模板包括 webpack 和 webpack-simple,前者是比较复杂专业的项目，他的配置并不全放在根目录下的 webpack.config.js 中。
----webpack-simple 相对简单的，它根目录下才有个 webpack.config.js。
4、注意：
项目建立过程中，有如下选择，选择NO。（该选项为使用ESLint规范你的代码，一个空格错误都将报错，不开启，避免不必要的麻烦）。
后两项为单元测试，可以选择No.
![](//files.jb51.net/file_images/article/201705/2017051714072413.png)


5、项目建立完成后，目录结构如下：
![](//files.jb51.net/file_images/article/201705/2017051714072414.png)


6、安装项目所需依赖，进入项目中：
```
npm install
```
完成后，会发现项目目录下多出一个node_modules文件夹，里面就是 vue-cli 创建的一个基于 webpack 的 vue.js 项目。


7、进入项目目录文件夹（my-project）中，就可以使用vue进行开发啦
8、使用npm run dev，便可以打开本地服务器实时查看效果（localhost:8080）
如果浏览器打开之后，没有加载出页面，有可能是本地的 8080 端口被占用，需要修改一下配置文件 config>index.js
建议将端口号改为不常用的端口。另外我还将 build 的路径前缀修改为 ' ./ '（原本为 ' / '），是因为打包之后，外部引入 js 和 css 文件时，如果路径以 ' / ' 开头，在本地是无法找到对应文件的（服务器上没问题）。
所以如果需要在本地打开打包后的文件，就得修改文件路径。


9、初始效果
![](//files.jb51.net/file_images/article/201705/2017051714072517.png)


10，退出监听，可以直接Ctrl+C，选择Y。


> ###### 以上就是本文全部内容，如果以上对你没有帮助，你可以自行去查阅其它对你帮助很大的文章。