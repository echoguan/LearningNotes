# 使用Git管理Hexo博客

## 概述
> Hexo部署到GitHub上的文件，是.md(即你的文章)转换之后的.html静态页面。

> 因此，如果想在不同的电脑上随时同步博客，就需要把Hexo博客的网站文件(即.md文件等等)存放到GitHub上管理。

> 而在仓库里新建一个分支存放来存放Hexo网站的文件则是一个十分方便的方式。**hexo branch -- 博客备份；master branch -- 发布网站。**

## 管理方式
1. 在你的GitHub Pages存放仓库，新建一个分支：hexo，并设置为默认分支。
> 因为我们只需要手动管理hexo分支上的文件，设为默认分支比较方便。

2. 在你本地的`echoguan.github.io`文件夹中，修改`_config.yml`文件中的`deploy`参数，`branch`为`master`。
> 把博客deploy到GitHub pages的时候会自动部署到配置的分支上。

3. 然后提交相关的网站文件到GitHub的hexo branch上。

## 其他电脑使用步骤
1. Clone Repository 到本地机器（此时为默认分支hexo）
2. 在本地`echoguan.github.io`文件夹下，执行
```
$ npm install
```
3. 再执行下列命令即可在[本地](http://localhost:4000/)查看博客
```
$ npm g
$ npm s
```
4. 其他代码同步、部署等操作直接执行即可


> 参考
> * 知乎 - [使用hexo，如果换了电脑怎么更新博客？](https://www.zhihu.com/question/21193762)
> * CrazyMilk - [GitHub Pages + Hexo搭建博客](http://crazymilk.github.io/2015/12/28/GitHub-Pages-Hexo%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2/)
