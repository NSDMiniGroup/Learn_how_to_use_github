# Git Introduce

## 初始化仓库
为了让Git工具能够管理一个仓库（文件夹），需要对目标仓库进行初始化。
```bash
git init
```
通过`ls -a`命名可以看到当前仓库会出现一个`.git`的文件夹，该文件夹将成为Git管理仓库的核心。

## 设置姓名和邮箱
名字和邮箱用于标识提交者，每一次的提交都会把这两个信息添加进去（并且是强制要求的）。注：这两个信息和github账户没有关联！
```bash
git config --system|global|local user.name "Yourname"
git config --system|global|local user.email "Youremail"
```
这个命令会将用户名、邮箱信息写入配置文件里。
注：
+ 使用`system`，配置信息则会写入到系统配置里面。例如，在Ubuntu下，会写入到`/etc/gitconfig`文件里面。(超级用户才允许写入)
+ 使用`global`，配置信息则会写入到用户配置文件里，例如，在Ubuntu下，则会写入到`~/.gitconfig`文件里面。（注不要在命令前加入sudo，否则写入的是sudo这个用户的用户配置文件里面）
+ 使用`local`，配置文件则会写入到当前初始化的仓库的配置里面，即`.git/config`中。（需要在仓库内部使用该命令)

## 设置color
可以通过设置`color.ui`来提高命令行输出的可读性，设置为`auto`即可。
```bash
git config --system|global|local color.ui auto
```
