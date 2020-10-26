环境准备：
```
linux
flink  https://mirrors.bfsu.edu.cn/apache/flink/flink-1.11.2/flink-1.11.2-bin-scala_2.12.tgz
kafka  https://mirrors.bfsu.edu.cn/apache/kafka/2.6.0/kafka_2.12-2.6.0.tgz
scala https://downloads.lightbend.com/scala/2.12.12/scala-2.12.12.tgz
java 1.8.0_91
```
本地安装

步骤一 安装包下载
```
# 检查java版本  要求 java8或11
$ java -version
# 下载flink安装包
$ tar -xzf flink-1.11.2-bin-scala_2.11.tgz
$ cd flink-1.11.2-bin-scala_2.11
```
步骤二 启动集群

```
$ ./bin/start-cluster.sh
Starting cluster.
Starting standalonesession daemon on host.
Starting taskexecutor daemon on host.
```

步骤三 提交一个job
```
$ ./bin/flink run examples/streaming/WordCount.jar
$ tail log/flink-*-taskexecutor-*.out
  (to,1)
  (be,1)
  (or,1)
  (not,1)
  (to,2)
  (be,2)

在web ui上查看job情况    localhost:8081
```

步骤四 关闭集群

```
$ ./bin/stop-cluster.sh
```