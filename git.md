## git

### 一. Git 安装

•使用前需要先安装 Git
•官网：https://www.git-scm.com/

安装成功后，桌面空白处鼠标右键显示如下：

![Alt text](imgs/00.png)

则表示安装成功。

### 二. Git 配置

•用户信息
  •$ git config --global user.name "用户名"
  •$ git config --global user.email "邮箱"


### 三. Git 本地操作

![Alt text](imgs/01.png)

#### 1、托管文件夹
创建你的空白文件夹，在文件夹中右键打开 git bash

#### 2、创建仓库
•Git 使用 git init 命令来初始化一个 Git 仓库
•Git 仓库会生成一个 .git 目录，该目录包含了资源的所有元数据，其他的项目目录保持不变

![Alt text](imgs/02.png)

#### 3、提交到本地仓库
•第一步：把当前文件夹中的所有文件，提交到暂存区
  •git add ./url 提交某个文件
  •git add ./ 提交所有文件

•第二步：把暂存区中的文件提交到本地仓库
  •git commit -m '提交的注释信息'
  •注意：每次提交都需要这两步。

![Alt text](imgs/03.png)


#### 4、状态查看
•git status 查看在你上次提交之后是否有对文件进行再次修改
•git status -s查看简短信息

#### 5、提交日志
•git log 查看历史提交记录
•git log --oneline查看历史记录的简洁的版本

![Alt text](imgs/04.png)

#### 6、回退版本
•git reset Head~1 回退到上一个版本，会保留历史记录
•git reset --hard Head~1 回退到指定版本，强制删除后续的历史记录，并且同时更新工作区

•git reflog 查看之前所有操作记录日志


#### 7、分支（Git的精髓）
•当你执行 git init 的时候，默认情况下 Git 就会为你创建 master 分支。
•master 分支是我们存储的主分支。
•实际工作中，我们是不允许在主分支中直接进行操作的。
•我们需要创建一些其他的临时分支进行操作，后期测试没有问题，才能将测试分支合并到主分支。

![Alt text](imgs/05.png)

查看分支 •git branch
创建分支 •git branch (branchname)
创建分支 •git checkout (branchname) 切换到指定分支

创建的新分支 会连带 master主分支 的历史记录

![Alt text](imgs/06.png)
![Alt text](imgs/07.png)

#### 8、合并分支
•临时分支中更改的内容包括历史信息，最终我们要在主分支中体现
•这就需要我们在主分支中合并临时分支（注意要切换到主分支）
•git merge [branchname] 将指定分支合并到当前分支
•合并完毕后，可以删除临时分支
•git branch -d [branchname]

![Alt text](imgs/08.png)

**合并冲突**
•两个分支合并过程中，如果修改了相同的位置或内容，这时会发生合并冲突。
•合并的结果中会标出冲突的内容，接下来需要我们手动处理这些冲突。
•最终解决冲突后，需要再次 add 和 commit ，提交最终版本。

![Alt text](imgs/09.png)
![Alt text](imgs/10.png)


## GitHub 远程托管平台
•一般我们的项目会托管到远程仓库中，便于多人协作开发。
•常用的在线托管平台：GitHub

Git 远端操作
![Alt text](imgs/11.png)

### 使用步骤
•1.打开 https://github.com/，在 GitHub 上创建一个远端仓库 “New repository”
![Alt text](imgs/12.png)

![Alt text](imgs/13.png)

•2.连接远端仓库，git remote add [shortname] [url]，可以指定一个简短的变量名将来指代远端仓库地址。

•3.如果本地没有这个项目，可以直接从远端仓库克隆到本地，git clone [url]。

•3.可以将本地仓库中的内容推送到远端仓库，git push -u origin master,推送到指定仓库的 master 分支。

•4.在第一次推送时，需要输入 GitHub 的账号和密码。

如果想把 其他分支 也上传到 同一个仓库，必须先切换到要上传的分支下：git push -u origin [新分支 dev]

•5.在本地仓库存在的情况下，也可以将远端仓库中的内容下拉到本地，git pull origin master,这个过程中会讲本地仓库和远端仓库最新分支版本进行合并。

•6.每次 push 之前，进行一次 pull，这样可以保留远程仓库的最新更新结果。

注意：
关于2021年8月13日github不再支持密码身份验证的解决方案：https://blog.csdn.net/weixin_41010198/article/details/119698015

## VScode 可视化操作 git
VScode 中将 git 中的常用操作进行了封装，我们可以通过直接点击功能按钮实现相关操作。

![Alt text](imgs/14.png)
![Alt text](imgs/15.png)
![Alt text](imgs/16.png)