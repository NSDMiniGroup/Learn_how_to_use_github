# Dive Into Github

## 设置SSH key
SSH协议可以用来连接以及认证远端的服务器和服务，在用SSH进行传输时，利用SSH密钥，我们可以无需在每次访问时提供用户名和访问令牌(token，可以理解为密码)（通常，我们的访问都是`PUSH、PULL操作)。可以先忽略这步，先体验体验推送时提供用户名和token的不方便之处再回过头来设置！
配置方法：[CONNECT WITH SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh)

## 克隆项目到本地

## 推送本地已存在仓库到远程新仓库
新建一个远程仓库：该仓库的名字最好和本地仓库保持一致。[Create a repo](https://docs.github.com/en/get-started/quickstart/create-a-repo)

为本地仓库添加远程仓库路径：可以添加多个远程仓库，远程仓库的路径可以在目标远程仓库的`Code``按钮下找到，https、ssh都可以。
```bash
git remote add <name> <url>
```
注：name参数的意思是为：为url所指示的远程仓库命名（标识），因为可以添加很多个远程仓库路径，name就是为了区分它们的。该命令会将信息写入到到本地仓库的config文件中(`.git/config`)。`git remote --help`可以获得更多的信息，但其他选项暂时用不到。

把本地仓库推送到远程仓库：
```bash
git push -u <remote_name> <local_branch_name>:<remote_branch_name>
```
注：remote_name是远程仓库名，local_branch_name则是想要推送的当前分支，remote_branch_name则是想要到的远程目的分支名;`-u`参数是用于创建local_branch与remote_branch的上流关系，简单地理解，就是当两条分支建立联系后，以后在local_branch上进行push、pull操作就可以省略参数。以上只是git push 的一种常用用法。

## 从远程仓库获取内容
```bash
git clone <url>
```
该命令默认把远程仓库的默认分支给克隆下来。
```bash
git branch -a
```
通过该命令可以查看克隆下来的目录的当前分支情况，`-a`参数可以同时显示本地仓库和远程仓库的分支信息。

如果想要获取远程的其他分支，则使用下面命令
```bash
git checkout -b <newbranch_name> <remote_name>/<remote_branch_name>
```
注：`git checkout -b <newbranch_name>` <=> `git branch <newbranch_name> && git checkout <newbranch_name>`。

## 获取最新的远程仓库分支
如果需要同步远程仓库的最新内容，可以使用下面的命令



