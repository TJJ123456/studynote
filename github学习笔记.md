*这个笔记基于《github入门与实践》*
## 第一章
- github的代码都由git管理，理解git是熟练运用github的关键，但git和gitbub是完全不同的东西
- 小团体开发可以建立Organization账户
- wiki用来写文档写手册

## 第二章 git的导入
- 集中型的代码会放到一个服务器里，服务器宕机就啥都没了
- git config --global color.ui auto 可以让命令输出有更高的可读性
- cat ~/.gitconfig 查看配置

## 第三章 前期准备
- 创建sshkey
    > ssh-keygen -t rsa -C "your_email@example.com"
- id_rsa文件是私有密钥，id_rsa.pub是公开密钥。在github中添加公开密钥，以后就可以用私有密钥进行认证了
    > 添加公开密钥方法 
    > - github 点击 Settings 选择SSH and GPGKeys菜单，点击 Add SSH Key
    > - key部分粘贴 cat ~/.ssh/id_rsa.pub 内容
    > ssh -T git@github.com 出现`Hi TJJ123456! You've successfully authenticated, but GitHub does not provide shell access.`就是和github认证和通信成功啦
- 创建仓库
    - New repository 
    - 钩readme 会自动初始化仓库并设置readme文件，让用户可以直接clone。。如果想向GitHub添加手中已有的Git仓库，建议不要勾选，直接手动push
    - Add .gitignore 这个设定会帮我们把不需要在Git仓库中进行版本管 理的文件记录在.gitignore文件中
    -  git clone git@github.com:hirocastest/studynote.git 
    - git add 将文件加入暂存区， git commit提交
    - git log 查看提交日志
        > MIT 许可协议具有以下特征。
        > - 被授权人权利：被授权人有权利使用、复制、修改、合并、出版发行、散布、 再授权和 / 或贩售软件及软件的副本，及授予被供应人同等权利，唯服从以下义务。 
        > - 被授权人义务：在软件和软件的所有副本中都必须包含以上版权声明和本许可 声明。 
        > - 其他重要特性：此许可协议并非属 copyleft 的自由软件许可协议条款，允许在 自由及开放源代码软件或非自由软件（proprietary…software）所使用。
        > - MIT的内容可依照程序著作权者的需求更改内容。此亦为MIT与BSD（The… BSD…license,…3-clause…BSD…license）本质上不同处。 
        > - MIT许可协议可与其他许可协议并存。另外，MIT条款也是自由软件基金会 （FSF）所认可的自由软件许可协议条款，与 GPL 兼容。 
    - git push github 上的仓库就会被更新

    ## 第四章 git基本操作
        ### 基本操作
        1. git status 查看仓库状态
        2. git add 向暂存区中添加文件
        3. git commit 保存仓库的历史纪录，通过记录，可以在工作树中复原文件
            -m 描述提交信息
        4. git log 查看提交日志
            --pretty=short 只显示提交信息的第一行 
            -p 前后差别
        5. git diff 查看前后差别（工作树）
            git diff HEAD 工作树和最新提交的差别

    ### 分支操作
        1. git branch 显示分支一览表
        2. git checkout -b XXX 创建、切换分支
            git branch xxx 创建分支
            git checkout xxx 切换分支
            git checkout -切换回上一个分支 
