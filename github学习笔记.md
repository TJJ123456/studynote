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
