# Hexo详解

## Hexo主要文目录
```
├── _config.yml     #网站的配置信息
├── package.json    #应用程序信息
├── scaffolds       #模板文件夹。新建文章时会使用这里的模版(可在_config.yml中配置)。
|   ├── page.md
|   └── ...
├── source          #资源文件夹。Markdowm和HTML文件会被解析到public文件夹中，而其他文件会拷贝过去。
|   ├── _drafts
|   └── _posts
└── themes          #主题文件夹。Hexo会根据使用的theme来生成静态页面。
```


> 参考
> * 嘟嘟MD - [hexo干货系列：（二）hexo主题下载及配置](http://tengj.top/2016/02/26/hexo2/)
