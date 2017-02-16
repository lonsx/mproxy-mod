# mproxy-mod
同时支持http和https自定义头域代理的mproxy实现。

## 使用
- 上传源码，秒编译一下：gcc -o mproxy mproxy.c 
- 启动mproxy：./mproxy -l 8080 -d 
- 关闭mproxy： ps -ef | grep mproxy | grep -v grep | cut -c 9-15 | xargs kill -s 9 
- 查看端口：netstat -tupnl 看到8080端口有了，就成功了，此端口支持同时代理包含'自定义头域'的HTTP和CONNECT流量。

## 对于云免应用

- 对于tiny：接入点APN可以设置cmnet加上127.0.0.1:65080的代理
- 文件中包含一个已失效的tiny模式示例
- 参考[云代理搭建](http://bybbs.org/read-65245-1.html)提到的教程

## 注意
- 源码中代理支持的自定义头域为'Lbxx:'，可以自行搜索源码，替换为其他任意5字节长度字符串，达到防盗用的目的。
- 模式中要求http部分Lbxx: [H]要紧跟Host:头域之后，https无要求
- 云免知识从八云论坛的蜡笔小新。同学处学得很多，谢谢！
- 源码修改自[examplecode/mproxy](https://github.com/examplecode/mproxy)，感谢！
