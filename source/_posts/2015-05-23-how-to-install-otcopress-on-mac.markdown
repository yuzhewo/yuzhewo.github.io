---
layout: post
title: "how to install otcopress on mac"
date: 2015-05-23 15:55:19 +0800
comments: true
categories: mac octopress
---

### 环境的配置
本地安装Octopress仅需要Git与Ruby两个软件  

Git环境监测
``` bash bash
git --version
git version 2.3.2 (Apple Git-55)
```
Ruby环境监测
```
ruby --version       
ruby 2.0.0p481 (2014-05-08 revision 45883) [universal.x86_64-darwin14]
```
如果提示未发现命令，自行查找安装方式  

### 安装Octopress  
1、克隆Octopress代码到本地  
```
git clone git://github.com/imathis/octopress.git octopress
Cloning into 'octopress'...
remote: Counting objects: 10795, done.
remote: Total 10795 (delta 0), reused 0 (delta 0), pack-reused 10795
Receiving objects: 100% (10795/10795), 2.84 MiB | 23.00 KiB/s, done.
Resolving deltas: 100% (5192/5192), done.
Checking connectivity... done.
```
2、切换到octopress目录，安装bundler  
```
octopress git:(master) sudo gem install bundler
Fetching: bundler-1.9.9.gem (100%)
Successfully installed bundler-1.9.9
Parsing documentation for bundler-1.9.9
Installing ri documentation for bundler-1.9.9
Done installing documentation for bundler after 5 seconds
1 gem installed
```

3、执行bundler安装命令，会执行速度非常慢
```
octopress git:(master) bundler install
Fetching gem metadata from https://rubygems.org/.........
```
打开项目目录下的Gemfile文件，修改gem源为http://ruby.taobao.org ，然后再次执行命令
``` yaml Gemfile
source "http://ruby.taobao.org"
```

3、安装默认主题  
```
octopress git:(master) ✗ rake install
## Copying classic theme into ./source and ./sass
mkdir -p source
cp -r .themes/classic/source/. source
mkdir -p sass
cp -r .themes/classic/sass/. sass
mkdir -p source/_posts
mkdir -p public
```

### 生成博客页与单页
生成静态页面
```
octopress git:(master) ✗ rake generate   
## Generating Site with Jekyll
directory source/stylesheets
    write source/stylesheets/screen.css
Configuration file: /Users/yuzhiguo/Source/GitHub/octopress/_config.yml
            Source: source
       Destination: public
      Generating... 
                    done.
 Auto-regeneration: disabled. Use --watch to enable.
```
开启预览服务
```
octopress git:(source) ✗ rake preview
Starting to watch source with Jekyll and Compass. Starting Rack on port 4000
Configuration file: /Users/yuzhiguo/Source/octopress/_config.yml
>>> Compass is watching for changes. Press Ctrl-C to Stop.
```
在浏览器中输入：[http://127.0.0.1:4000](http://127.0.0.1:4000)

参考网站：  
http://ruby.taobao.org/  
http://octopress.org/docs/setup/  
https://git-scm.com/download/mac  
https://www.ruby-lang.org/en/documentation/installation/#homebrew

 

