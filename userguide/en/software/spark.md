## Spark Example ##

### Config and Start Spark Standalone Cluster

The spark [official document](http://spark.apache.org/docs/latest/spark-standalone.html) provides guides about how to start a standalone cluster.

In Docklet, Apache Spark is installed in `/home/spark` .

Assume user `robin` has a Workspace named `note`. There are three vnode in the vcluster: host-0, host-1, host-2.

`robin` opens Web Terminal, entering Spark home directory, starting spark master

```
root@host-0:~# cd /home/spark
root@host-0:/home/spark# ./sbin/start-master.sh
```

once started, `robin` could enter `logs` directory to check logs. Spark master 
will print its working URL `spark://HOST:PORT`,  used for connections by
spark slaves. Here it may be `spark://host-0:7077`. The master WEB UI is
also printed, probably `http://host-0:8080`.

Then start spark slaves in host-1 and host-2 using ssh

```
root@host-0:/home/spark# ssh root@host-1 /home/spark/sbin/start-slave.sh spark://host-0:7077
root@host-0:/home/spark# ssh root@host-2 /home/spark/sbin/start-slave.sh spark://host-0:7077
```

Done, the cluster is ready.

** Note **

Docklet provides two scripts in `sbin` for fast starting and stop spark clusters. The `dl_start_spark.sh` can automatically start a spark cluster, the master of which is host-0, and all vnodes are slaves. The `dl_stop_spark.sh` can stop the spark cluster started by `dl_start_spark.sh`.

Now running an example 

```
root@host-0:/home/spark# ./bin/spark-submit --master spark://host-0:7077 examples/src/main/python/pi.py 10
```

### WEB UI

Docklet vcluster is in private network, which could not be
accessed from public Internet. Docklet provides a proxy service to help
visiting Web Server in the vcluster from outside.

In Docklet portal, click ** Config ** to configure visiting Spark WEB UI.

Assume the IP address of host-0 is 172.16.0.99

Configure ** Service ** 

ip : 172.16.0.99, port : 8080

Click ** Enable ** . Now the Spark WEB UI can be accessed through the  URL of

`http://portal/_web/robin/note` .


From WEB UI, `robin` could check the information about the Spark cluster, including workers, jobs, etc.

