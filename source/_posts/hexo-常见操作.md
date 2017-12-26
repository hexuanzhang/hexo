---
title: hexo 常见操作
date: 2017-11-03 11:08:28
updated_at: 2017-12-20 10:53:17
tags: [hexo]
categories: [hexo]
---

## 写博客
1. hexo new

    ```
    hexo new post title
    ```
    >   post 一般可以省略
    >   
    >   如果 title 中包含空格，则需要用双引号包含
    >   >   hexo new post 'New Blog'
    >
    >   执行后，会在 `source/_post` 文件夹下生成一个 `new-Blog.md` 的文件

2. 编辑
    
    >   编辑 `new-Blog.md` 文件，书写博客内容
    
3. 发布
    
    >   执行 `hexo g` 生成静态页面
    >
    >   执行 `hexo s` 启动本地服务器查看效果
    >
    >   执行 `hexo d` 发布文章至 `Github`
    >   >   hexo d [-m "commit message"]

## 写草稿

```
hexo new draft title
```

>   新创建的草稿将保存到 `source/_drafts` 文件夹中
> 
>   草稿默认不显示在页面中，可以通过执行上述命令时添加 `--draft` 参数，或者把 `_config.yml` 中 `render_drafts` 参数设为 `true` 来预览草稿
> 
>   可以通过 `publish` 命令将草稿移至 `source/_post` 文件夹中
>   >   hexo publish draft title

## 删除博客
>   直接在 `source/_post` 文件夹中删除对应的 `.md` 文件
> 
>   执行 `hexo g` 和 `hexo d`

## 添加标签
*   添加标签页
   
    1.  创建 `tags` 页面
    
        ```
        hexo new page tags
        ```
    2.  编辑新创建的 `tags` 页面，修改页面类型为 `tags`，主题将自动为这个页面显示所有标签

        ```
        title: 分类
        date: 2017-11-03 14:25:07
        type: "tags"
        comments: false
        ```
    3. 在菜单中添加链接，编辑主题的 `_config.yml`，去掉 `menu` 中 `tags: /tags` 的注释
        
        ```
        menu:
        home: /
        categories: /categories
        archives: /archives
        tags: /tags
        ```

*   博客加标签

    >   在 `Front-matter` 区域中指定 `tags`
    
    ```
    tags: [label, label, label]
    
    tags: 
    - label
    - label
    ```

## 添加分类
*   添加分类页
   
    1.  创建 `categories` 页面
    
        ```
        hexo new page categories
        ```
    2.  编辑新创建的 `categories` 页面，修改页面类型为 `categories`，主题将自动为这个页面显示所有分类

        ```
        title: 分类
        date: 2017-11-03 14:25:07
        type: "categories"
        comments: false
        ```
    3. 在菜单中添加链接，编辑主题的 `_config.yml`，去掉 `menu` 中 `categories: /categories` 的注释
        
        ```
        menu:
        home: /
        categories: /categories
        archives: /archives
        tags: /tags
        ```
*   博客加标签

    >   在 `Front-matter` 区域中指定 `categories`
    
    ```
    categories: [label, label, label]
    
    categories: 
    - label
    - label
    ```

## 关闭底部主题信息
>   将主题（`next`）配置文件 `_config.yml` 中的以下字段设为 `false`
>   >   
```   
footer:
    powered: false
    theme:
        enable: false
        version: false
```

## 统计
>   对博客的统计，可以通过 [busuanzi](http://busuanzi.ibruce.info/) 和 [leancloud](https://leancloud.cn) 实现
> 
>   最新版本的 `next` 主题支持上面两种方式，只需要修改配置文件 `_config.yml` 即可

```
# leancloud
/* app_id 和 app_key 通过 注册 leancloud 获取 */

leancloud_visitors:
  enable: true
  app_id: 
  app_key: 
```

```
# busuanzi

busuanzi_count:
  # count values only if the other configs are false
  enable: true
  # custom uv span for the whole site
  site_uv: true
  site_uv_header: <i class="fa fa-user"></i>
  site_uv_footer:
  # custom pv span for the whole site
  site_pv: true
  site_pv_header: <i class="fa fa-eye"></i>
  site_pv_footer:
  # custom pv span for one page only
  page_pv: false
  page_pv_header: <i class="fa fa-file-o"></i>
  page_pv_footer:
```

## RSS 订阅
*   安装插件
    
    ```
    npm install hexo-generator-feed --save
    ```
*   开启网站 RSS 支持

    >   修改博客配置文件 `_config.yml`
    
    ```
    # RSS
    ## Plugins: http://hexo.io/plugins/
    plugin:
      - hexo-generator-feed
    #Feed Atom
    feed:
    type: atom
    path: atom.xml
    limit: 20
    ```
*   开启主题 RSS 支持

    >   不同主题开启方法不同，NexT 主题默认开启，其它主题参考对应的主题说明
    
*   生产 RSS

    ```
    hexo clean
    hexo g
    ```

## Gitment 评论
>   `Gitment` 是一款基于 `GitHub Issues` 的评论系统。支持在前端直接引入，不需要任何后端代码。可以在页面进行登录、查看、评论、点赞等操作，同时有完整的 Markdown / GFM 和代码高亮支持。尤为适合各种基于 GitHub Pages 的静态博客或项目页面

1. 注册 OAuth Application
    
    >   注册一个新的 [OAuth Application](https://github.com/settings/applications/new)
    >  
    >   `callback URL` 对应的是博客域名
    >
    >   注册成功之后将得到一个 `Client ID
` 和 `Client Secret`
    
    ![](http://blog-1255677601.cossh.myqcloud.com/blog/2017-12-26-082909.jpg)
    ![](http://blog-1255677601.cossh.myqcloud.com/blog/2017-12-26-082912.jpg)
2. 开启 Gitment
    >   编辑主题配置文件 `_config.yml` 文件
    
    ```
    # Gitment
    # Introduction: https://imsun.net/posts/gitment-introduction/
    gitment:
        enable: true
        mint: true 
        count: true 
        lazy: false 
        cleanly: true 
        language: zh-Hans 
        github_user: # github name
        github_repo: # 博客域名
        client_id: # 注册 OAuth Application 得到的 client_id
        client_secret: # 注册 OAuth Application 得到的 client_secret
    ```

## 畅言评论
*   注册登录畅言评论官网
*   设置网站信息
    
    ![](http://blog-1255677601.cossh.myqcloud.com/blog/2017-12-26-082913.jpg)
    
*   获取 APP ID 和APP KEY 
    
    ![](http://blog-1255677601.cossh.myqcloud.com/blog/2017-12-26-082915.jpg)
    
*   修改主题配置文件 _config.yml
    
    ![](http://blog-1255677601.cossh.myqcloud.com/blog/2017-12-26-082917.jpg)
    
*   重新发布

    ![](http://blog-1255677601.cossh.myqcloud.com/blog/2017-12-26-082918.jpg)

