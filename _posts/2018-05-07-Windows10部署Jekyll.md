---
layout: post
title: Windows10部署Jekyll
date: 2018-05-07 
tags: Jekyll   
---

# 介绍

>&nbsp;&nbsp;&nbsp;&nbsp; Jekyll 是一个简单的博客形态的静态站点生产机器。它有一个模版目录，其中包含原始文本格式的文档，通过 Markdown （或者 Textile）以及 Liquid 转化成一个完整的可发布的静态网站，你可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 GitHub Page 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是完全免费。
>&nbsp;&nbsp;&nbsp;&nbsp; 使用 Jekyll 搭建博客之前要确认下本机环境，[Git](https://git-scm.com/ "Git") 环境（用于部署到远端）、[Ruby](http://www.ruby-lang.org/en/downloads/) 环境（Jekyll 是基于 Ruby 开发的）、包管理器 [RubyGems](http://rubygems.org/pages/download) 等。   


## 安装步骤

* 安装Ruby
* 安装Devkit
* 安装Jekyll


### 1、安装Ruby

下载地址：[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)
![](/images/posts/jekyll/image_0.png)

注意版本要选 2.0 到 3.0 之间，本文使用的是：rubyinstaller-2.2.6-x64
![](/images/posts/jekyll/image_1.png)

安装路径自定义，比如我的路径是：（本文章命令运行在Git bash,将Git添加到默认路径后,鼠标右击即可出现 Git Bash Here）

```
#Ruby安装在D盘，可通过一下命令查看。
$ cd D:
$ cd Ruby22-x64

```

检查ruby是否正常安装，会出现版本号

```
$ ruby -v 
```
>#######运行结果
>ruby 2.2.6p396 (2016-11-15 revision 56800) [x64-mingw32]


### 2、安装DevKit
下载地址：[https://rubyinstaller.org/downloads/](https://rubyinstaller.org/downloads/)
在刚才网站向下滑动页面。
![](/images/posts/jekyll/image_2.png)

解压文件，路径不要太长，推荐：(D:\DevKit)
```
#D:\DevKit

$ cd D:
$ cd DevKit
$ ruby dk.rb init  #初始化

	#Initialization complete! Please review and modify the auto-generated 'config.yml' file to ensure it contains the root directories to all of the installed Rubies you want enhanced by the DevKit.

#完成初始化后使用记事本或notepad++打开 config.yml ，然后在最后一行添加 -D:/Ruby22-x64 

$ ruby dk.rb review  # 审查（非必须）
	#Based upon the settings in the 'config.yml' file generated
	#from running 'ruby dk.rb init' and any of your customizations,
	#DevKit functionality will be injected into the following Rubies
	#when you run 'ruby dk.rb install'

$ ruby dk.rb install  # 安装
	#[INFO] Updating convenience notice gem override for 'D:/Ruby22-x64'
	#[INFO] Installing 'D:/Ruby22-x64/lib/ruby/site_ruby/devkit.rb'

$ gem -v  # 查看gem是否正常安装
	#2.4.5.2
```

###3、安装jekyll

```
$ gem install jekyll
	#Successfully installed safe_yaml-1.0.4
	Successfully installed rouge-3.1.1
	Successfully installed forwardable-extended-2.6.0
	Successfully installed pathutil-0.16.1
	Successfully installed mercenary-0.3.6
	Successfully installed liquid-4.0.0
	Successfully installed kramdown-1.16.2
	Successfully installed ruby_dep-1.5.0
	Successfully installed ffi-1.9.23-x64-mingw32
	Successfully installed rb-inotify-0.9.10
	Successfully installed rb-fsevent-0.10.3
	Successfully installed listen-3.1.5
	Successfully installed jekyll-watch-2.0.0
	Successfully installed sass-listen-4.0.0
	Successfully installed sass-3.5.6
	Successfully installed jekyll-sass-converter-1.5.2
	Successfully installed concurrent-ruby-1.0.5
	Successfully installed i18n-0.9.5
	Successfully installed eventmachine-1.2.6-x64-mingw32
	Temporarily enhancing PATH to include DevKit...
	Building native extensions.  This could take a while...
	Successfully installed http_parser.rb-0.6.0
	Successfully installed em-websocket-0.5.1
	Successfully installed colorator-1.1.0
	Successfully installed public_suffix-3.0.2
	Successfully installed addressable-2.5.2
	Successfully installed jekyll-3.8.1
	Parsing documentation for safe_yaml-1.0.4
	Installing ri documentation for safe_yaml-1.0.4
	Parsing documentation for rouge-3.1.1
	Installing ri documentation for rouge-3.1.1
	Parsing documentation for forwardable-extended-2.6.0
	Installing ri documentation for forwardable-extended-2.6.0
	Parsing documentation for pathutil-0.16.1
	Installing ri documentation for pathutil-0.16.1
	Parsing documentation for mercenary-0.3.6
	Installing ri documentation for mercenary-0.3.6
	Parsing documentation for liquid-4.0.0
	Installing ri documentation for liquid-4.0.0
	Parsing documentation for kramdown-1.16.2
	Installing ri documentation for kramdown-1.16.2
	Parsing documentation for ruby_dep-1.5.0
	Installing ri documentation for ruby_dep-1.5.0
	Parsing documentation for ffi-1.9.23-x64-mingw32
	Installing ri documentation for ffi-1.9.23-x64-mingw32
	Parsing documentation for rb-inotify-0.9.10
	Installing ri documentation for rb-inotify-0.9.10
	Parsing documentation for rb-fsevent-0.10.3
	Installing ri documentation for rb-fsevent-0.10.3
	Parsing documentation for listen-3.1.5
	Installing ri documentation for listen-3.1.5
	Parsing documentation for jekyll-watch-2.0.0
	Installing ri documentation for jekyll-watch-2.0.0
	Parsing documentation for sass-listen-4.0.0
	Installing ri documentation for sass-listen-4.0.0
	Parsing documentation for sass-3.5.6
	Installing ri documentation for sass-3.5.6
	Parsing documentation for jekyll-sass-converter-1.5.2
	Installing ri documentation for jekyll-sass-converter-1.5.2
	Parsing documentation for concurrent-ruby-1.0.5
	Installing ri documentation for concurrent-ruby-1.0.5
	Parsing documentation for i18n-0.9.5
	Installing ri documentation for i18n-0.9.5
	Parsing documentation for eventmachine-1.2.6-x64-mingw32
	Installing ri documentation for eventmachine-1.2.6-x64-mingw32
	Parsing documentation for http_parser.rb-0.6.0
	Installing ri documentation for http_parser.rb-0.6.0
	Parsing documentation for em-websocket-0.5.1
	Installing ri documentation for em-websocket-0.5.1
	Parsing documentation for colorator-1.1.0
	Installing ri documentation for colorator-1.1.0
	Parsing documentation for public_suffix-3.0.2
	Installing ri documentation for public_suffix-3.0.2
	Parsing documentation for addressable-2.5.2
	Installing ri documentation for addressable-2.5.2
	Parsing documentation for jekyll-3.8.1
	Installing ri documentation for jekyll-3.8.1
	Done installing documentation for safe_yaml, rouge, forwardable-extended, pathutil, mercenary, liquid, kramdown, ruby_dep, ffi, rb-inotify, rb-fsevent, listen, jekyll-watch, sass-listen, sass, jekyll-sass-converter, concurrent-ruby, i18n, eventmachine, http_parser.rb, em-websocket, colorator, public_suffix, addressable, jekyll after 68 seconds
	25 gems installed

$ gem install bundler
	#Successfully installed bundler-1.16.1
	Parsing documentation for bundler-1.16.1
	Installing ri documentation for bundler-1.16.1
	Done installing documentation for bundler after 18 seconds
	1 gem installed

$ gem install github-pages
	#invalid options: -SHN
	(invalid options are ignored)
	Successfully installed mini_portile2-2.3.0
	Nokogiri is built with the packaged libraries: libxml2-2.9.7, libxslt-1.1.32, zlib-1.2.11, libiconv-1.15.
	Successfully installed nokogiri-1.8.2-x64-mingw32
	Successfully installed unicode-display_width-1.3.2
	Successfully installed terminal-table-1.8.0
	Successfully installed rouge-2.2.1
	Successfully installed public_suffix-2.0.5
	Successfully installed jekyll-3.7.3
	Successfully installed jekyll-seo-tag-2.4.0
	Successfully installed jekyll-theme-time-machine-0.1.1
	Successfully installed jekyll-theme-tactile-0.1.1
	Successfully installed jekyll-theme-slate-0.1.1
	Successfully installed jekyll-theme-modernist-0.1.1
	Successfully installed jekyll-theme-minimal-0.1.1
	Successfully installed jekyll-theme-midnight-0.1.1
	Successfully installed jekyll-theme-merlot-0.1.1
	Successfully installed jekyll-theme-leap-day-0.1.1
	Successfully installed jekyll-theme-hacker-0.1.1
	Successfully installed jekyll-theme-dinky-0.1.1
	Successfully installed jekyll-theme-cayman-0.1.1
	Successfully installed jekyll-theme-architect-0.1.1
	Successfully installed multipart-post-2.0.0
	Successfully installed faraday-0.15.0
	Successfully installed sawyer-0.8.1
	Successfully installed octokit-4.8.0
	Successfully installed jekyll-github-metadata-2.9.4
	Successfully installed jekyll-theme-primer-0.5.3
	Successfully installed jekyll-swiss-0.4.0
	Successfully installed jekyll-feed-0.9.3
	Successfully installed minima-2.4.1
	Successfully installed thread_safe-0.3.6
	Successfully installed tzinfo-1.2.5
	Successfully installed activesupport-4.2.9
	Successfully installed jekyll-titles-from-headings-0.5.1
	Successfully installed jekyll-default-layout-0.1.4
	Successfully installed jekyll-readme-index-0.2.0
	Successfully installed jekyll-optional-front-matter-0.3.0
	Successfully installed jekyll-relative-links-0.5.3
	-------------------------------------------------
	Thank you for installing html-pipeline!
	You must bundle Filter gem dependencies.
	See html-pipeline README.md for more details.
	https://github.com/jch/html-pipeline#dependencies
	-------------------------------------------------
	Successfully installed html-pipeline-2.8.0
	Successfully installed jekyll-mentions-1.3.0
	Successfully installed gemoji-3.0.0
	Successfully installed jemoji-0.9.0
	Successfully installed ethon-0.11.0
	Successfully installed typhoeus-1.3.0
	Successfully installed rubyzip-1.2.1
	Successfully installed jekyll-remote-theme-0.2.3
	Successfully installed jekyll-avatar-0.5.0
	Successfully installed coffee-script-source-1.11.1
	Successfully installed execjs-2.7.0
	Successfully installed coffee-script-2.4.1
	Successfully installed jekyll-coffeescript-1.1.1
	Successfully installed jekyll-paginate-1.1.0
	Successfully installed jekyll-gist-1.5.0
	Successfully installed jekyll-sitemap-1.2.0
	Successfully installed jekyll-redirect-from-0.13.0
	Installing dnsruby...
	  For issues and source code: https://github.com/alexdalitz/dnsruby
	  For general discussion (please tell us how you use dnsruby): https://groups.google.com/forum/#!forum/dnsruby
	Successfully installed dnsruby-1.60.2
	Successfully installed github-pages-health-check-1.7.3
	Successfully installed ruby-enum-0.7.2
	Temporarily enhancing PATH to include DevKit...
	Building native extensions.  This could take a while...
	Successfully installed commonmarker-0.17.9
	Successfully installed jekyll-commonmark-1.2.0
	Successfully installed jekyll-commonmark-ghpages-0.1.5
	Successfully installed github-pages-183
	Parsing documentation for mini_portile2-2.3.0
	Installing ri documentation for mini_portile2-2.3.0
	Parsing documentation for nokogiri-1.8.2-x64-mingw32
	Installing ri documentation for nokogiri-1.8.2-x64-mingw32
	Parsing documentation for unicode-display_width-1.3.2
	Installing ri documentation for unicode-display_width-1.3.2
	Parsing documentation for terminal-table-1.8.0
	Installing ri documentation for terminal-table-1.8.0
	Parsing documentation for rouge-2.2.1
	Installing ri documentation for rouge-2.2.1
	Parsing documentation for public_suffix-2.0.5
	Installing ri documentation for public_suffix-2.0.5
	Parsing documentation for jekyll-3.7.3
	Installing ri documentation for jekyll-3.7.3
	Parsing documentation for jekyll-seo-tag-2.4.0
	Installing ri documentation for jekyll-seo-tag-2.4.0
	Parsing documentation for jekyll-theme-time-machine-0.1.1
	Installing ri documentation for jekyll-theme-time-machine-0.1.1
	Parsing documentation for jekyll-theme-tactile-0.1.1
	Installing ri documentation for jekyll-theme-tactile-0.1.1
	Parsing documentation for jekyll-theme-slate-0.1.1
	Installing ri documentation for jekyll-theme-slate-0.1.1
	Parsing documentation for jekyll-theme-modernist-0.1.1
	Installing ri documentation for jekyll-theme-modernist-0.1.1
	Parsing documentation for jekyll-theme-minimal-0.1.1
	Installing ri documentation for jekyll-theme-minimal-0.1.1
	Parsing documentation for jekyll-theme-midnight-0.1.1
	Installing ri documentation for jekyll-theme-midnight-0.1.1
	Parsing documentation for jekyll-theme-merlot-0.1.1
	Installing ri documentation for jekyll-theme-merlot-0.1.1
	Parsing documentation for jekyll-theme-leap-day-0.1.1
	Installing ri documentation for jekyll-theme-leap-day-0.1.1
	Parsing documentation for jekyll-theme-hacker-0.1.1
	Installing ri documentation for jekyll-theme-hacker-0.1.1
	Parsing documentation for jekyll-theme-dinky-0.1.1
	Installing ri documentation for jekyll-theme-dinky-0.1.1
	Parsing documentation for jekyll-theme-cayman-0.1.1
	Installing ri documentation for jekyll-theme-cayman-0.1.1
	Parsing documentation for jekyll-theme-architect-0.1.1
	Installing ri documentation for jekyll-theme-architect-0.1.1
	Parsing documentation for multipart-post-2.0.0
	Installing ri documentation for multipart-post-2.0.0
	Parsing documentation for faraday-0.15.0
	Installing ri documentation for faraday-0.15.0
	Parsing documentation for sawyer-0.8.1
	Installing ri documentation for sawyer-0.8.1
	Parsing documentation for octokit-4.8.0
	Installing ri documentation for octokit-4.8.0
	Parsing documentation for jekyll-github-metadata-2.9.4
	Installing ri documentation for jekyll-github-metadata-2.9.4
	Parsing documentation for jekyll-theme-primer-0.5.3
	Installing ri documentation for jekyll-theme-primer-0.5.3
	Parsing documentation for jekyll-swiss-0.4.0
	Installing ri documentation for jekyll-swiss-0.4.0
	Parsing documentation for jekyll-feed-0.9.3
	Installing ri documentation for jekyll-feed-0.9.3
	Parsing documentation for minima-2.4.1
	Installing ri documentation for minima-2.4.1
	Parsing documentation for thread_safe-0.3.6
	Installing ri documentation for thread_safe-0.3.6
	Parsing documentation for tzinfo-1.2.5
	Installing ri documentation for tzinfo-1.2.5
	Parsing documentation for activesupport-4.2.9
	Installing ri documentation for activesupport-4.2.9
	Parsing documentation for jekyll-titles-from-headings-0.5.1
	Installing ri documentation for jekyll-titles-from-headings-0.5.1
	Parsing documentation for jekyll-default-layout-0.1.4
	Installing ri documentation for jekyll-default-layout-0.1.4
	Parsing documentation for jekyll-readme-index-0.2.0
	Installing ri documentation for jekyll-readme-index-0.2.0
	Parsing documentation for jekyll-optional-front-matter-0.3.0
	Installing ri documentation for jekyll-optional-front-matter-0.3.0
	Parsing documentation for jekyll-relative-links-0.5.3
	Installing ri documentation for jekyll-relative-links-0.5.3
	Parsing documentation for html-pipeline-2.8.0
	Installing ri documentation for html-pipeline-2.8.0
	Parsing documentation for jekyll-mentions-1.3.0
	Installing ri documentation for jekyll-mentions-1.3.0
	Parsing documentation for gemoji-3.0.0
	Installing ri documentation for gemoji-3.0.0
	Parsing documentation for jemoji-0.9.0
	Installing ri documentation for jemoji-0.9.0
	Parsing documentation for ethon-0.11.0
	Installing ri documentation for ethon-0.11.0
	Parsing documentation for typhoeus-1.3.0
	Installing ri documentation for typhoeus-1.3.0
	Parsing documentation for rubyzip-1.2.1
	Installing ri documentation for rubyzip-1.2.1
	Parsing documentation for jekyll-remote-theme-0.2.3
	Installing ri documentation for jekyll-remote-theme-0.2.3
	Parsing documentation for jekyll-avatar-0.5.0
	Installing ri documentation for jekyll-avatar-0.5.0
	Parsing documentation for coffee-script-source-1.11.1
	Installing ri documentation for coffee-script-source-1.11.1
	Parsing documentation for execjs-2.7.0
	Installing ri documentation for execjs-2.7.0
	Parsing documentation for coffee-script-2.4.1
	Installing ri documentation for coffee-script-2.4.1
	Parsing documentation for jekyll-coffeescript-1.1.1
	Installing ri documentation for jekyll-coffeescript-1.1.1
	Parsing documentation for jekyll-paginate-1.1.0
	Installing ri documentation for jekyll-paginate-1.1.0
	Parsing documentation for jekyll-gist-1.5.0
	Installing ri documentation for jekyll-gist-1.5.0
	Parsing documentation for jekyll-sitemap-1.2.0
	Installing ri documentation for jekyll-sitemap-1.2.0
	Parsing documentation for jekyll-redirect-from-0.13.0
	Installing ri documentation for jekyll-redirect-from-0.13.0
	Parsing documentation for dnsruby-1.60.2
	Installing ri documentation for dnsruby-1.60.2
	Parsing documentation for github-pages-health-check-1.7.3
	Installing ri documentation for github-pages-health-check-1.7.3
	Parsing documentation for ruby-enum-0.7.2
	Installing ri documentation for ruby-enum-0.7.2
	Parsing documentation for commonmarker-0.17.9
	Installing ri documentation for commonmarker-0.17.9
	Parsing documentation for jekyll-commonmark-1.2.0
	Installing ri documentation for jekyll-commonmark-1.2.0
	Parsing documentation for jekyll-commonmark-ghpages-0.1.5
	Installing ri documentation for jekyll-commonmark-ghpages-0.1.5
	Parsing documentation for github-pages-183
	Installing ri documentation for github-pages-183
	Done installing documentation for mini_portile2, nokogiri, unicode-display_width, terminal-table, rouge, public_suffix, jekyll, jekyll-seo-tag, jekyll-theme-time-machine, jekyll-theme-tactile, jekyll-theme-slate, jekyll-theme-modernist, jekyll-theme-minimal, jekyll-theme-midnight, jekyll-theme-merlot, jekyll-theme-leap-day, jekyll-theme-hacker, jekyll-theme-dinky, jekyll-theme-cayman, jekyll-theme-architect, multipart-post, faraday, sawyer, octokit, jekyll-github-metadata, jekyll-theme-primer, jekyll-swiss, jekyll-feed, minima, thread_safe, tzinfo, activesupport, jekyll-titles-from-headings, jekyll-default-layout, jekyll-readme-index, jekyll-optional-front-matter, jekyll-relative-links, html-pipeline, jekyll-mentions, gemoji, jemoji, ethon, typhoeus, rubyzip, jekyll-remote-theme, jekyll-avatar, coffee-script-source, execjs, coffee-script, jekyll-coffeescript, jekyll-paginate, jekyll-gist, jekyll-sitemap, jekyll-redirect-from, dnsruby, github-pages-health-check, ruby-enum, commonmarker, jekyll-commonmark, jekyll-commonmark-ghpages, github-pages after 96 seconds
	61 gems installed

$ jekyll -v  #查看jekyll版本信息
	#jekyll 3.8.1

```
可以切换到任意clone的xxxxxxxxxx.github.io目录下运行jekyll
```
$ jekyll serve   #jekyll server两个命令都可以

	#Configuration file: D:/GitHub/xxxxxxxxxx.github.io/_config.yml
	Deprecation: The 'gems' configuration option has been renamed to 'plugins'. Please update your config file accordingly.
	Source: D:/GitHub/xxxxxxxxxx.github.io
	Destination: D:/GitHub/xxxxxxxxxx.github.io/_site
	Incremental build: disabled. Enable with --incremental
	Generating...
	done in 0.72 seconds.
	Please add the following to your Gemfile to avoid polling for changes:
	gem 'wdm', '>= 0.1.0' if Gem.win_platform?
	Auto-regeneration: enabled for 'D:/GitHub/xxxxxxxxxx.github.io'
	Server address: http://127.0.0.1:4000
	Server running... press ctrl-c to stop.
```

# Q&A

## 1、更换镜源

####在Git Bash运行下面三条命令
```
$ gem sources --remove https://rubygems.org/
$ gem sources -a http://gems.ruby-china.org/
$ gem sources -l
```
会出现如下结果：

> \*\*\* CURRENT SOURCES \*\*\*
>
>http://gems.ruby-china.org/

## 2、jekyll本地浏览器无法预览中文blog

####修改安装目录\Ruby22-x64\lib\ruby\2.2.0\webrick\httpservlet\filehandler.rb  
(建议先备份filehandler.rb)
找到下列两处，添加一句（各添加一行命令）
 
1.
> path=req.path_info.dup.force_encoding(Encoding.find("filesystem"))

>path.force_encoding("UTF-8") # 添加部分编码  

>if trailing_pathsep?(req.path_info)

2.
>break if base == "/"
>
>base.force_encoding("UTF-8") #添加部分编码
>
>break unless File.directory?(File.expand_path(res.filename+base))