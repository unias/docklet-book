## Spark 示例 ##

### 配置与启动

Apache Spark 缺省安装于 `/home/spark` 目录.

假定用户 `robin` 的 Workspace 为 `note`, 有3个vnode: host-0, host-1, host-2, 
构成一个私有vcluster集群.

`robin` 打开 Web Terminal, 进入Spark主目录, 启动spark master

```
root@host-0:~# cd /home/spark
root@host-0:/home/spark# ./sbin/start-master.sh
```

启动后, 可进入 `logs` 目录查看启动日志, spark master 会打印其工作URL, 
`spark://HOST:PORT`,  用于 spark slave 进行连接，此处应该是
`spark://host-0:7077`。master 的WEB UI 地址则为 `http://host-0:8080`。

通过 ssh 在 host-1, host-2 上启动 spark slave.

```
root@host-0:/home/spark# ssh root@host-1 /home/spark/sbin/start-slave.sh spark://host-0:7077
root@host-0:/home/spark# ssh root@host-2 /home/spark/sbin/start-slave.sh spark://host-0:7077
```

运行一个示例

```
root@host-0:/home/spark# ./bin/spark-submit --master spark://host-0:7077 examples/src/main/python/pi.py 10
```

### WEB UI

左边栏进入Docklet ** Config ** 界面, 配置从浏览器里访问 Spark WEB UI

假定 host-0 的IP地址为 172.16.0.99

则配置 ** Service ** 

设置 ip : 172.16.0.99, port : 8080

点击 ** Enable ** 后, 即可通过上方 URL

`http://portal/_web/robin/note`

访问 Spark 的 WEB UI

可看到该Spark Cluster的Workers, 以及运行的作业情况。

