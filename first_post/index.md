# First_post


文章简介：netstat -s 已经废弃，一些机器已经不内置，但 ss 和 nstat 是内置的。本文通过代码描述他俩之间迁移的方法。

netstat -s 读取 /proc/net/netstat，所有参数会由这个 table 对应起来，进而展示 右侧人可读信息。代码见 这里。

说结论吧：

例如：

1
2
netstat -s | grep -i 'invalid SYN cookies received'
    87441 invalid SYN cookies received
在 这里 搜索 invalid SYN cookies received 可以看到如下内容：

1
{"SyncookiesFailed", N_("%llu invalid SYN cookies received"), opt_number},
可以看到 SyncookiesFailed，则对应的更现代的 nstat 对应起来就是：

1
2
nstat -s -za | grep SyncookiesFailed
TcpExtSyncookiesFailed          87441              0.0
结果 87441 可以对应上。

