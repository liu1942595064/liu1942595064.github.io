---
title: 主题踩坑补充
date: 2021/09/13 22:11:08
update: 2021/09/13
categories:
 - [计算机科学, 二进制杂谈, Theme Shoka Documentation]
tags:
 - Hexo
sticky: true
valine:
  placeholder: "1. 提问前请先仔细阅读本文档⚡\n2. 页面显示问题💥，请提供控制台截图📸或者您的测试网址\n3. 其他任何报错💣，请提供详细描述和截图📸，祝食用愉快💪"
---



:::info
这篇文章是为了解决原作者遗留下来的问题帮助大家减少踩坑而写的 。后续可能会随主题的变更而继续踩坑解决问题。

相信大家也和我一样网上找的教程有些和本主题相关不大，导致一直解决不了问题，如果您有幸找到我，那么恭喜你，你应该减少了找 **解决问题** 的时间。
:::



# `mermaid`流程图显示

> 注：操作之前，请先把该安装的插件安装好。

1. 主题根目录找到 **node_modules**

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie0.PNG)

2. 在主题根目录 node_modules 下找到相关的“旧”的 puppeteer 然后全部删除

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie1.PNG)

3. 全部删完后 在 bash 里设置镜像地址

```bash
PUPPETEER_DOWNLOAD_HOST=https://storage.googleapis.com.cnpmjs.org
```

4. 设置完之后 下载 Puppeteer

```bash
npm install puppeteer
```

5. 下载好后，返回 [流程2]{.pink} 继续找相关的 puppeteer 相关的字眼，找到后只复制 `puppeteer` ，注意没有后缀等其它字符，只单独复制它 。

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie2.PNG)

6. 再继续返回 [流程2]{.pink} 找到 `hexo-renderer-multi-markdown-it` ，把它打开。

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie3.PNG)

7. 打开后找到 node_modules ，打开它，注意是 [流程6]{.pink} 下的 。

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie4.PNG)

8. 打开后可以看到在这目录下有个 命名为 puppeteer 的文件夹。把当前的 puppeteer 文件夹覆盖为 [流程5]{.pink} 所复制的 puppeteer 文件夹，就成功了。可以显示 mermaid 流程图了。就是这么简单，我也没想到，我之前整得太复杂了......

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie5.PNG)

![puppeteer-jie0](https://cdn.jsdelivr.net/gh/liu1942595064/cdn@master/lvsheng/puppeteer-jie6.PNG)



:::warning
更多踩坑请期待更新......
:::

