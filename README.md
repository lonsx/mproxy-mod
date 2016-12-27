# mproxy-mod
同时支持http和https自定义字段代理的mproxy实现。

## 使用
- 上传源码，秒编译一下：gcc -o mproxy mproxy.c 
- 启动mproxy：./mproxy -l 8080 -d 
- 关闭mproxy： ps -ef | grep mproxy | grep -v grep | cut -c 9-15 | xargs kill -s 9 
- 查看端口：netstat -tupnl 看到8080端口有了，就成功了，此端口支持同时代理包含'自定义字段'的HTTP和CONNECT流量。

## 对于tiny云免应用

- 接入点APN可以设置cmnet加上127.0.0.1:65080的代理
- 文件中包含一个已失效的tiny模式示例

## 注意
- 源码中代理支持的自定义字段为'Lbxx:'，可以自行替换为其他任意5字节长度字符串，达到防盗用的目的。
- 源码修改自[examplecode/mproxy](https://github.com/examplecode/mproxy)，感谢！
