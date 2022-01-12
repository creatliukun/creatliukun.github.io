---
layout: post
title:  "mac从0到1搭建jekyll项目"
date:   2022-01-11 18:32:18 +0800
categories: jekyll update
---

```
现在的问题是我的代码推上去了，但是hexo deploy部署失败了，不知道是怎么回事，少了一些参数
Conversion error: Jekyll::Converters::Scss encountered an error while converting 'assets/css/style.scss':
                    No such file or directory @ dir_chdir - /github/workspace/docs
```


``` bash
mac安装brew(亲测)
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
安装ruby
brew install ruby
# 添加ruby路径到环境变量
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
然后在终端查看ruby安装位置与版本信息:
which ruby 
ruby -v
使用ruby的包管理器gem安装Jekyll及bundle(这一步如果速度慢的话可以添加ruby的国内源镜像)
# 移除默认镜像
sudo gem sources --remove https://rubygems.org/
# 添加国内镜像
sudo gem sources -a http://gems.ruby-china.com/
# 查看镜像列表
gem sources -l
# 安装bundler和jekyll
sudo gem install --user-install bundler jekyll
# 安装缺失的包(也可以视情况安装,看看后面会不会因为这个包而报错)
sudo gem install webrick
# 将gem安装的包路径添加到环境变量
echo 'export PATH="$HOME/.gem/ruby/3.0.0/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
最后可以通过gem env检查路径是否正确(正确的话会在路径中显示安装gem包的家目录)

安装完成后只要通过jekyll new name命令即可创建一个新的博客站点
jekyll new blog
cd blog
启动：
bundle exec jekyll serve

报错
 Please append `--trace` to the `serve` command
                     for any additional information or backtrace.
从 Ruby 3.0 开始 webrick 已经不在绑定到 Ruby 中了，请参考链接： Ruby 3.0.0 Released 中的说明。webrick 需要手动进行添加
bundle add webrick
在清空一下，重新执行
jekyll clean
bundle exec jekyll serve

上线
git init
git remote add origin https://github.com/xxx/xxx.github.io.git
git pull origin master

编辑.gitignore文件，将_site、.sass-cache及.jekyll-metadata加入到其中（生成博客的时候默认会生成，但可能会被git所覆盖，若覆盖只需重新编辑即可
 _site
.sass-cache
.jekyll-metadata


运行项目
jekyll s / jekyll serve

```
