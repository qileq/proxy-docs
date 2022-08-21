# 代理整理

鉴于 GFW 浪费了笔者大量时间，故整理下笔者使用过的工具、软件的代理设置姿势。下文均默认以 socks5 列出配置。

## Maven
[Configuring a proxy](https://maven.apache.org/guides/mini/guide-proxies.html):
```xml
<proxies>
	<proxy>
		<id>example-proxy</id>
		<active>true</active>
		<protocol>socks5</protocol>
		<host>10.211.55.4</host>
		<port>1080</port>
		<username>proxyuser</username>
		<password>somepassword</password>
		<nonProxyHosts>www.google.com|*.github.com|*.apache.org</nonProxyHosts>
	</proxy>
</proxies>
```

## Git
```
Host git.xxxx.corp.com
    HostName git.xxxx.corp.com
    User xxx
    IdentityFile  ~/.ssh/id_rsa
    ProxyCommand  /usr/bin/nc -v -X 5 -x 10.211.55.4:1080 %h %p
```

