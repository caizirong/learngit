# [安装](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000)
# 创建版本库
* 首先创建一个空目录
    ```
   git mkdir learngit
    cd learngit
    pwd
    ```
*  把目录变成git可以管理的仓库
    `git init`
* 新建一个readme.txt文件，格式为UTF-8 Without BOM，保存在learngit目录
* 添加到版本库
    ```git add readme.txt```
* 提交到仓库
    ```git commit -m "wrote a readme file"```
# 时光穿梭机
* ```git status```查看状态
* ```git diff```查看修改内容
   ## 版本回退
   * ```git log```查看日志（即提交历史），用来回退到哪个版本
   * ```git reflog```查看命令历史，用来回退到以前版本后重新回退到新的版本
   * ```git reset --hard commit_id```用来回退版本
   * ```git reset --hard HEAD^```回退到最近一次
    ## 工作区和暂存区
    * 再次修改readme.txt，同时新增新文件LICENSE.txt,用git status 可以看到原来的readme change,而新增的文件是untracked
    * 通过git add 把这两个文件加到暂存区stage，重新git status，看到change not commit
    * 一次性用git commit -m 提交到工作区master
    ## 管理修改
    * 要么add一次commit一次，要么全部add在commit，add后不commit用git status会发现没有变化
    ## 撤销修改
    * 只是在工作区修改，没有git add：```git checkout -- readme.txt```丢弃修改
    * 在工作区修改并git add到stage：```git reset HEAD readme.txt```，然后在```git checkout -- readme.txt```
    * 修改后git add并git comit -m到master，使用版本回退（前提是没提交远程仓库）
    ## 删除文件
    * 新增文件test.txt,git add test.txt，git commit -m "add test.txt"，这样文件就在版本库里了
    * 删除这个文件```rm test.txt```
    * 确实想删除，```git rm test.txt```，```git commit -m "remove test.txt"```
    * 删错了，因为提交到版本库，所有可以恢复，但只能恢复到最新版本，会丢失最近一次提交后修改的内容 ```git checkout -- test.txt```
# 远程仓库
   * ```ssh-keygen -t -rsa -C "caizirongczr@gmail.com"```
   在.ssh目录下打开id_rsa.pub，复制key添加到github
    ## 添加远程库
    * 连接远程仓库
   ```git remote add origin git@github.com:caizirong/learngit.git```
    第一次push到远程库
        ``` git push -u origin master```
    之后本地修改了，git add及git commit进行本地提交后，
        ```git push origin master```
    ## 从远程库克隆
       先在github上创建一个新仓库，勾选initialize....
       ```git clone git@github.com:caizirong/gitskills.git```
# 分支管理
