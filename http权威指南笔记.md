*先挖个坑*
*本笔记基于《http权威指南》2012*

# 第一部分

## 第一章 http概述
- http使用的是可靠的数据传输协议，开发人员只需要注重于应用程序特有细节的编写

- http仔细地给每种要通过web传输的对象都打上了名为MIME类型的数据格式标签,web服务器会为所有http对象数据附加一个MIME类型
MIME类型是一种文本标记
    > html格式的文本由 text/html类型标记<br>
    > ascII文本由 text/plain类型标记
    > jpeg image/jpeg <br>
    > gif image/gif <br>
    > ......

    ### URI
        Uniform Resource Identifier 统一资源标识符
        URI分为url和urn,几乎所有uri都是url
        url 第一部分 http 被称为方案
            第二部分 www.xxxx.com 给出了服务器地址
            第三部分 /xxxx 指定了web服务器的某个资源

- 事务 <br>
    一个http事务由一条客户端往服务端的请求命令和从服务器发回客户端的响应结果组成 <br>
    完成一项任务时通常会发布多个http事务。web浏览器会发布一系列HTTP事务来获取并显示一个包含了丰富图片的web页面
    ### http方法（发往服务端）
        get 
        put
        delete
        post
        head
    ### 状态码

    ### 报文
        请求报文
        GET /xxx HTTP/1.0
        Accept: text/*
        Accept-Language: en,fr

        响应报文
        HTTP/1.0 200 OK //起始行
        Content-type: text/plain //首部
        Content-length: 19
            //空行
        Hi! I'm your daddy! //主体

- 连接 <br>
    http是应用层协议，把联网的细节都交给了tcp/ip协议 <br>
    tcp提供了
    > 无差错的数据传输 <br>
    > 按序输出 <br>
    > 未分段的数据流 <br>
    在http客户端发送报文之前，需要用网际协议(IP)地址和端口号在客户端和服务端之间建立一条tcp/ip连接
    
- web的结构组件
    - 代理 <br>
        位于客户端和服务器之间，接受所有客户端的http请求，将这些请求转发给服务器
    - 缓存 <br>
        特殊的http代理服务器，保存常用文档本地副本以提高性能的代理缓存
    - 网关 gateway <br>
        特殊的服务器
    - 隧道
        建立起来后，会在两条连接之间对原始数据进行盲转发的http应用程序。我不理解
    - Agent代理
        代表用户发起http请求的客户端程序。

## 第二章 URL与资源
- URL的语法 
    - 方案 <br>
        由第一个字母号开始，由第一个“：”符号将其与URL的其余部分分隔开。大小写无关
    - 主机与端口 <br>
        由主机名或者IP地址来表示主机名 <br>
        www.xxxxxxxx.com:80 <br>
        xxx.xx.xx.xxx:80
    - 用户名和密码 <br>
        如果有，在主机名前面，用户名和密码用“：”分隔 <br>
        anonymous:password
    - 路径 <br>
        说明了资源位于服务器的什么地方<br>
        如/xxx.html
    - 参数 <br>
        向应用程序提供它们所需的输入参数，以便正确地与服务端进行交互<br>
        由字符“;”将其与URL的其余部分分割开来。<br>
        如 ftp://xxxx.xx.xx/xxx;type=d <br>
        或者两段 ftp://xxx.xxx/xxx;sale=false/xxx.html;type=d
    - 查询字符串
        “?"右边的部分被称为查询（query）组件。
