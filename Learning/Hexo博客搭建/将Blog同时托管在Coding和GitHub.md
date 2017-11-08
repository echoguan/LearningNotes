# 将Blog同时托管在Coding和GitHub

> 由于GitHub毕竟是国外网站，访问速度上略慢，而且GitHub屏蔽了百度爬虫，所以我们再将博客部署到国内的托管平台Coding。

### Coding配置
1. 如果没有Coding账号，注册一个。
2. 在Coding上新建一个项目。
  * 项目名称建议与用户名相同。这样在访问 [yourusername.coding.me](yourusername.coding.me)就可以访问博客；否则还需要带上项目名，即访问[yourusername.coding.me/项目名](yourusername.coding.me/项目名)才能访问到你的博客。
  * 项目设置为私有
  * 如果是第一次使用Coding，需要设置SSH公钥。可以参考[配置 SSH 公钥访问代码仓库](https://coding.net/help/doc/account/ssh-key.html)

### `_config.yml`配置
为了同时可以部署到两个平台，就需要`_config.yml`的`deploy`属性
* 需要修改为如下格式：

```
deploy:
  type: git
  message: [message]
  repo:
    github: <repository url>,[branch]
    gitcafe: <repository url>,[branch]

```

* 例如修改为：

```
deploy:
  type: git
  repo:
    github: https://github.com/echoguan/echoguan.github.io.git,master
    coding: git@git.coding.net:echoguan/echoguan.git,master
```

### Pages服务方式部署
* 此处使用较为简单的静态Pages部署方式。分支来源选择master即可。
* 至此，访问[yourusername.coding.me](yourusername.coding.me)就可以看到你在Coding上的博客啦。

## References
> * xiaocai - [hexoBlog托管在coding](https://learnerzxc.github.io/2017/11/02/hexoBlog%E6%89%98%E7%AE%A1%E5%9C%A8coding/)
> * 嘟嘟MD - [hexo干货系列：（四）将hexo博客同时托管到github和coding](http://tengj.top/2016/03/06/hexo4/#)
