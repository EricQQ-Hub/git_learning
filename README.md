# git_learning
# https://git-scm.com/book/zh/v2
git
Name: Eric Chen
Email: xfnuaa@qq.com

一、git简介
    1 Git是目前世界上最先进的分布式版本控制系统（没有之一）。
    2 Git记录了仓库（项目）的修改过程
    ...

二、安装git
    1 官网直接下载安装
    2 配置主机信息
        git config --global usr.name "name"
        git config --global usr.email "email"

三、利用 github创建版本库（强烈建议）
    1 在github上创建一个新的库
        eg: git_learning
    2 git clone 该库到本地
        git clone git@github.com:EricQQ-Hub/git_learning.git
        warning:  一定要选择 SSH 通道！！！
    3 创建一个新的文件 1.py  2.py
        3.0 打开 git bash
            $ touch 1.py
            $ touch 2.py
        3.1 将新建文件加入到 暂存空间
            git add filename1 filename2 ...
            git add 1.py 2.py
        3.2 创建修改记录"create 1.py 2.p"
            git commit -m "修改提示信息"
            git commit -m "create 1.py 2.py"
        3.3 修改 1.py
            在1.py 中写入：print("hello world!")
            git add 1.py
            git commit -m "hello 1.py"
        3.4 其他常用的git command
            git status  查看仓库中文件的修改状态
            git diff 若文件发生改变，通过改命令，可查看文件与最近版本的差异

四、版本穿梭管理
    1 git log命令显示从最近到最远的提交日志
        5c51331 (HEAD -> master, origin/master, origin/HEAD) add name and email
        6957da2 create 1.py
        8687215 Initial commit
         ----  HEAD 指向当前所在版本   add name and email

    2 git reset -hard commit_id/HEAD~n/HEAD^


            
五、远程管理 ---- 将本地的版本发布到github
    1 配置SSH
        1.1 github SSH配置
        --->ssh-keygen -t rsa -C "xfnuaa@qq.com"
            生成SSH
            本地私有密钥：/c/Users/Eric/.ssh/id_rsa
            远程公有秘钥：/c/Users/Eric/.ssh/id_rsa.pub
        --->登陆GitHub，打开“Account settings”，“SSH Keys”页面：
            然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
        1.2 本地 SSH配置
        若 ssh -v git@github.com
            上述命令执行后，出现的提示最后两句是没有更多的身份验证方法可以试权限被拒绝（publickey）。
        那么
            ssh-add ~/c/Users/Eric/.ssh/id_rsa
        执行 ssh -v git@github.com 不会报错
        1.3  将本地版本发布到github
        --->git pull origin master   
        --->git push -u origin master
        
六、分支管理


        