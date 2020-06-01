# 利用Hexo + github搭建免费个人博客

## 写在前面

作为一个前端小菜鸟，一直想搭建一个自己的blog，用来整理收录日常遇到的问题、技术点以及学习笔记，然后便有了这篇文章，
作为搭建博客完成的第一篇文章。

## Github相关操作

- 首先注册github账号，这里就不多讲了，[点击这里](https://github.com/)，进入官网注册
- 创建自己的仓库，这里需要注意的是，个人仓库名需要是 **github昵称.github.io** 或者 **github昵称.github.com**
- 生成及添加秘钥，后续用来文章的无密提交，当然可以使用http链接来提交，只不过每次需要填写账号密码
<!--more-->
## Hexo安装前置

- 安装Node.js [点击进入官网](https://nodejs.org/en/)
- 安装Git [点击进入官网](https://git-scm.com/downloads)

## Hexo安装及配置

- [Hexo官网](https://hexo.io/zh-cn/)
- 下载安装Hexo
  ```
    npm install -g hexo-cli
  ```
- 安装完成后，终端输入 hexo ，出现如下图，说明安装成功

  {% asset_img hexo_i_suc.jpg %}

- 初始化博客
  ```
    // 初始化blog,创建blog文件夹，
    hexo init <文件夹名称>
    cd <文件夹名称>
    // 安装依赖
    npm install
  ```
- 在刚创建的文件夹目录下，安装Deployer，用来连接github上传文章
  ```
    // 终端运行
    npm install hexo-deployer-git --save
  ```

- 配置博客

  附上官网相关配置信息 [点击进入](https://hexo.io/zh-cn/docs/configuration.html)

  为了修改后方便提交，我们对博客进行相应的配置，找到_config.yml文件，用记事本或者IDE打开

- 修改博客的相关信息，找到如下信息，进行修改

  {% asset_img hexo_site_config.jpg %}

- 配置部署github信息
  ```
    deploy:
      type: git
      repo: 博客项目的ssh地址
      branch: master
  ```

## 文章发表

- 创建文章，可手动在 **/source/_posts** 文件夹下创建md文件，也可以执行下面命令
  ```
    hexo new "文章标题"
  ```
- 打开刚刚创建的文章，修改文章内容为 hello hexo

- 保存后本地终端运行:
  ```
    hexo server
  ```
- 打开本地代理地址，打开浏览器中，输入http://localhost:4000/

- 上传文章到github，终端执行如下命令
  ```
    hexo g
    hexo d
    or 
    hexo g -d
  ```

参考[Hexo官方文档](https://hexo.io/zh-cn/docs/index.html)

